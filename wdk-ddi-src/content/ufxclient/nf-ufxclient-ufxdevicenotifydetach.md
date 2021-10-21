---
UID: NF:ufxclient.UfxDeviceNotifyDetach
title: UfxDeviceNotifyDetach function (ufxclient.h)
description: Notifies UFX that the device's USB cable has been detached.
old-location: buses\ufxdevicenotifydetach.htm
tech.root: usbref
ms.date: 09/14/2021
keywords: ["UfxDeviceNotifyDetach function"]
ms.keywords: UfxDeviceNotifyDetach, UfxDeviceNotifyDetach method [Buses], buses.ufxdevicenotifydetach, ufxclient/UfxDeviceNotifyDetach
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UfxDeviceNotifyDetach
 - ufxclient/UfxDeviceNotifyDetach
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ufxclient.h
api_name:
 - UfxDeviceNotifyDetach
---

# UfxDeviceNotifyDetach function

## -description

Notifies UFX that the device's USB cable has been detached.

## -parameters

### -param UfxDevice

[in]
A handle to a UFX device object that the driver created by calling [UfxDeviceCreate](./nf-ufxclient-ufxdevicecreate.md).

## -remarks

This method is called by the client driver when it receives a USB cable detach event. Once the detach event is processed, all endpoints should be disabled and device should move to a low power mode.

The client driver typically calls **UfxDeviceNotifyDetach** from its [EVT_WDF_INTERRUPT_DPC](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc.md) callback function, as shown in the following example.

```cpp
VOID 
DeviceInterrupt_EvtInterruptDpc (
    _In_ WDFINTERRUPT Interrupt,
    _In_ WDFOBJECT AssociatedObject
    )
/*++

Routine Description:

    'EVT_WDF_INTERRUPT_DPC' handler for the device interrupt object.
    https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc

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
}
```