---
UID: NF:ufxclient.UfxDeviceNotifyAttach
title: UfxDeviceNotifyAttach function
author: windows-driver-content
description: Notifies UFX that the device's USB cable has been attached.
old-location: buses\ufxdevicenotifyattach.htm
old-project: usbref
ms.assetid: E45FA08C-3E00-4AF6-A983-6E9C808AFA11
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UfxDeviceNotifyAttach, UfxDeviceNotifyAttach method [Buses], buses.ufxdevicenotifyattach, ufxclient/UfxDeviceNotifyAttach
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDeviceNotifyAttach
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxDeviceNotifyAttach function


## -description


Notifies UFX that the device's  USB cable has been attached.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This method does not return a value.




## -remarks



When the client driver calls <b>UfxDeviceNotifyAttach</b>, the USB function class extension (UFX) does the following:

<ul>
<li>Moves the device to the <i>Powered</i> state, as defined in the USB specification.</li>
<li>Allows device enumeration to occur.</li>
</ul>
The client driver typically calls <b>UfxDeviceNotifyAttach</b> from its <a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a> callback function, as shown in the following example.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID 
DeviceInterrupt_EvtInterruptDpc (
    _In_ WDFINTERRUPT Interrupt,
    _In_ WDFOBJECT AssociatedObject
    )
/*++

Routine Description:

    'EvtInterruptDpc' handler for the device interrupt object.
    http://msdn.microsoft.com/en-us/library/windows/hardware/ff541721(v=vs.85).aspx

Arguments:

    Interrupt - Associated interrupt object.

    AssociatedObject - FDO Object

--*/
{
    WDFDEVICE WdfDevice;
    PDEVICE_INTERRUPT_CONTEXT InterruptContext;
    PCONTROLLER_CONTEXT ControllerContext;
    BOOLEAN Attached;
    BOOLEAN GotAttachOrDetach;
    CONTROLLER_EVENT ControllerEvent;

    UNREFERENCED_PARAMETER(Interrupt);

    TraceEntry();

    WdfDevice = (WDFDEVICE) AssociatedObject;
    ControllerContext = DeviceGetControllerContext(WdfDevice);

    WdfSpinLockAcquire(ControllerContext-&gt;DpcLock);

    WdfInterruptAcquireLock(ControllerContext-&gt;DeviceInterrupt);
    Attached = ControllerContext-&gt;Attached;
    GotAttachOrDetach = ControllerContext-&gt;GotAttachOrDetach;
    ControllerContext-&gt;GotAttachOrDetach = FALSE;
    WdfInterruptReleaseLock(ControllerContext-&gt;DeviceInterrupt);

    //
    // Handle attach/detach events
    //
    if (GotAttachOrDetach) {
        if (Attached &amp;&amp; ControllerContext-&gt;WasAttached) {
            //
            // We must have gotten at least one detach. Need to reset the state.
            //        
            ControllerContext-&gt;RemoteWakeupRequested = FALSE;
            ControllerContext-&gt;Suspended = FALSE;
            UfxDeviceNotifyDetach(ControllerContext-&gt;UfxDevice);
        }

        if (Attached) {
            ControllerContext-&gt;RemoteWakeupRequested = FALSE;
            ControllerContext-&gt;Suspended = FALSE;
            UfxDeviceNotifyAttach(ControllerContext-&gt;UfxDevice);
        }
    }

    ControllerContext-&gt;WasAttached = Attached;

    InterruptContext = DeviceInterruptGetContext(ControllerContext-&gt;DeviceInterrupt);

    //
    // #### TODO: Insert code to read and dispatch events from the controller ####
    // 

    // The sample will assume an endpoint event of EndpointEventTransferComplete
    ControllerEvent.Type = EventTypeEndpoint;
    ControllerEvent.u.EndpointEvent = EndpointEventTransferComplete;
    
    //
    // Handle events from the controller
    //
    switch (ControllerEvent.Type) {
    case EventTypeDevice:
        HandleDeviceEvent(WdfDevice,  ControllerEvent.u.DeviceEvent);
        break;

    case EventTypeEndpoint:
        HandleEndpointEvent(WdfDevice, ControllerEvent.u.EndpointEvent);
        break;
    }

    WdfSpinLockRelease(ControllerContext-&gt;DpcLock);

    TraceExit();
}</pre>
</td>
</tr>
</table></span></div>


