---
UID: NC:ufxclient.EVT_UFX_DEVICE_HOST_CONNECT
title: EVT_UFX_DEVICE_HOST_CONNECT (ufxclient.h)
description: The client driver's implementation to initiate connection with the host.
old-location: buses\evt_ufx_device_host_connect.htm
tech.root: usbref
ms.date: 01/18/2022
keywords: ["EVT_UFX_DEVICE_HOST_CONNECT callback function"]
ms.keywords: EVT_UFX_DEVICE_HOST_CONNECT, EVT_UFX_DEVICE_HOST_CONNECT callback, EvtUfxDeviceHostConnect, EvtUfxDeviceHostConnect callback function [Buses], PFN_UFX_DEVICE_HOST_CONNECT, PFN_UFX_DEVICE_HOST_CONNECT callback function pointer [Buses], buses.evt_ufx_device_host_connect, ufxclient/EvtUfxDeviceHostConnect
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UFX_DEVICE_HOST_CONNECT
 - ufxclient/EVT_UFX_DEVICE_HOST_CONNECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ufxclient.h
api_name:
 - EVT_UFX_DEVICE_HOST_CONNECT
---

# EVT_UFX_DEVICE_HOST_CONNECT callback function

## -description

The client driver's implementation to initiate connection with the host.

## -parameters

### -param unnamedParam1 [in]

The handle to a USB device object that the client driver received in a previous call to the [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md) method.

## -remarks

The client driver for the function host controller registers its *EVT_UFX_DEVICE_HOST_CONNECT* implementation with the USB function class extension (UFX) by calling the [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md) method.

The client driver must not initiate connection with the host until UFX invokes this  event callback. The client driver shall indicate completion of this event by calling the [UfxDeviceEventComplete](nf-ufxclient-ufxdeviceeventcomplete.md) method.

### Examples

```cpp
EVT_UFX_DEVICE_HOST_CONNECT UfxDevice_EvtDeviceHostConnect;

VOID
UfxDevice_EvtDeviceHostConnect (
    _In_ UFXDEVICE UfxDevice
    )
/*++

Routine Description:

    EvtDeviceHostConnect callback handler for UFXDEVICE object.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

--*/
{
    PCONTROLLER_CONTEXT ControllerContext;
    PUFXDEVICE_CONTEXT DeviceContext;
    BOOLEAN EventComplete;

    TraceEntry();

    DeviceContext = UfxDeviceGetContext(UfxDevice);
    ControllerContext = DeviceGetControllerContext(DeviceContext->FdoWdfDevice);

    EventComplete = TRUE;

    WdfSpinLockAcquire(ControllerContext->DpcLock);

    //
    // #### TODO: Insert code to set the run state on the controller ####
    //

    WdfSpinLockRelease(ControllerContext->DpcLock);

    if (EventComplete) {
        UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);
    }

    TraceExit();
}

```

## -see-also

- [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md)
- [UfxDeviceEventComplete](nf-ufxclient-ufxdeviceeventcomplete.md)
