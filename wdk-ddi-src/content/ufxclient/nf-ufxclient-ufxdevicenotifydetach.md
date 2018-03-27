---
UID: NF:ufxclient.UfxDeviceNotifyDetach
title: UfxDeviceNotifyDetach function
author: windows-driver-content
description: Notifies UFX that the device's USB cable has been detached.
old-location: buses\ufxdevicenotifydetach.htm
old-project: usbref
ms.assetid: 890C7451-D9BF-4019-ABBE-D97446728E6B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UfxDeviceNotifyDetach, UfxDeviceNotifyDetach method [Buses], buses.ufxdevicenotifydetach, ufxclient/UfxDeviceNotifyDetach
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
-	UfxDeviceNotifyDetach
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxDeviceNotifyDetach function


## -description


Notifies UFX that the device's  USB cable has been detached.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This method does not return a value.




## -remarks



This method is called by the client driver when it receives a USB cable detach event. Once the detach event is processed, all endpoints should be disabled and device should move to a low power mode.

The client driver typically calls <b>UfxDeviceNotifyDetach</b> from its <a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a> callback function, as shown in the following example.

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


