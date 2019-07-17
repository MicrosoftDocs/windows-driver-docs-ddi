---
UID: NF:ufxclient.UfxDeviceNotifyDetach
title: UfxDeviceNotifyDetach function (ufxclient.h)
description: Notifies UFX that the device's USB cable has been detached.
old-location: buses\ufxdevicenotifydetach.htm
tech.root: usbref
ms.assetid: 890C7451-D9BF-4019-ABBE-D97446728E6B
ms.date: 05/07/2018
ms.keywords: UfxDeviceNotifyDetach, UfxDeviceNotifyDetach method [Buses], buses.ufxdevicenotifydetach, ufxclient/UfxDeviceNotifyDetach
ms.topic: function
f1_keywords:
 - "ufxclient/UfxDeviceNotifyDetach"
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
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ufxclient.h
api_name:
- UfxDeviceNotifyDetach
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxDeviceNotifyDetach function


## -description


Notifies UFX that the device's  USB cable has been detached.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


## -returns



This method does not return a value.




## -remarks



This method is called by the client driver when it receives a USB cable detach event. Once the detach event is processed, all endpoints should be disabled and device should move to a low power mode.

The client driver typically calls <b>UfxDeviceNotifyDetach</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function, as shown in the following example.

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
    https://msdn.microsoft.com/library/windows/hardware/ff541721(v=vs.85).aspx

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

    WdfSpinLockAcquire(ControllerContext->DpcLock);

    WdfInterruptAcquireLock(ControllerContext->DeviceInterrupt);
    Attached = ControllerContext->Attached;
    GotAttachOrDetach = ControllerContext->GotAttachOrDetach;
    ControllerContext->GotAttachOrDetach = FALSE;
    WdfInterruptReleaseLock(ControllerContext->DeviceInterrupt);

    //
    // Handle attach/detach events
    //
    if (GotAttachOrDetach) {
        if (Attached && ControllerContext->WasAttached) {
            //
            // We must have gotten at least one detach. Need to reset the state.
            //        
            ControllerContext->RemoteWakeupRequested = FALSE;
            ControllerContext->Suspended = FALSE;
            UfxDeviceNotifyDetach(ControllerContext->UfxDevice);
        }

        if (Attached) {
            ControllerContext->RemoteWakeupRequested = FALSE;
            ControllerContext->Suspended = FALSE;
            UfxDeviceNotifyAttach(ControllerContext->UfxDevice);
        }
    }

    ControllerContext->WasAttached = Attached;

    InterruptContext = DeviceInterruptGetContext(ControllerContext->DeviceInterrupt);

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

    WdfSpinLockRelease(ControllerContext->DpcLock);

    TraceExit();
}</pre>
</td>
</tr>
</table></span></div>


