---
UID: NC:ufxclient.EVT_UFX_DEVICE_PORT_CHANGE
title: EVT_UFX_DEVICE_PORT_CHANGE (ufxclient.h)
description: The client driver's implementation to update the type of the new port to which the USB device is connected.
old-location: buses\evt_ufx_device_port_change.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UFX_DEVICE_PORT_CHANGE callback function"]
ms.keywords: EVT_UFX_DEVICE_PORT_CHANGE, EVT_UFX_DEVICE_PORT_CHANGE callback, EvtUfxDevicePortChange, EvtUfxDevicePortChange callback function [Buses], PFN_UFX_DEVICE_PORT_CHANGE, PFN_UFX_DEVICE_PORT_CHANGE callback function pointer [Buses], buses.evt_ufx_device_port_change, ufxclient/EvtUfxDevicePortChange
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UFX_DEVICE_PORT_CHANGE
 - ufxclient/EVT_UFX_DEVICE_PORT_CHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ufxclient.h
api_name:
 - PFN_UFX_DEVICE_PORT_CHANGE
---

# EVT_UFX_DEVICE_PORT_CHANGE callback function


## -description

The client driver's implementation to update the type of the new port to which the USB device is connected.

## -parameters

#### - NewPort [in]

A USBFN_PORT_STATE-typed flag that indicates the type of the new port.


#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.

## -remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_PORT_CHANGE</i> implementation with the USB function class extension (UFX) by calling the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a> method.

UFX invokes this event callback to inform the client driver about the new state of the device.

The client driver indicates completion of this event by calling the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a> method.


#### Examples


```

EVT_UFX_DEVICE_PORT_CHANGE UfxDevice_EvtDevicePortChange;

VOID
UfxDevice_EvtDevicePortChange (
    _In_        UFXDEVICE UfxDevice,
    _In_        USBFN_PORT_TYPE NewPort
    )
/*++

Routine Description:

    EvtDevicePortChange handler for the UFXDEVICE object.
    Caches the new port type, and stops or resumes idle as needed.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    NewPort - New port type

--*/
{
    NTSTATUS Status;
    PUFXDEVICE_CONTEXT Context;

    PAGED_CODE();

    TraceEntry();

    Context = UfxDeviceGetContext(UfxDevice);

    TraceInformation("New PORT: %d", NewPort);

    //
    //  #### TODO: Insert code to examine the device USB state and port type 
    //      and determine if it needs to stop or resume idle.


    UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);
    TraceExit();
}
```


## -see-also

<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>



<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a>
