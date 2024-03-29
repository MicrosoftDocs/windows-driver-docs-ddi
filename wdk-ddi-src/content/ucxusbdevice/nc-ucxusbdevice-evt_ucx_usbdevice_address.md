---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ADDRESS
title: EVT_UCX_USBDEVICE_ADDRESS (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to address the USB device.
old-location: buses\evt_ucx_usbdevice_address.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UCX_USBDEVICE_ADDRESS callback function"]
ms.keywords: EVT_UCX_USBDEVICE_ADDRESS, EVT_UCX_USBDEVICE_ADDRESS callback, EvtUcxUsbDeviceAddress, EvtUcxUsbDeviceAddress callback function [Buses], PEVT_UCX_USBDEVICE_ADDRESS, PEVT_UCX_USBDEVICE_ADDRESS callback function pointer [Buses], buses.evt_ucx_usbdevice_address, ucxusbdevice/EvtUcxUsbDeviceAddress
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_USBDEVICE_ADDRESS
 - ucxusbdevice/EVT_UCX_USBDEVICE_ADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxusbdevice.h
api_name:
 - EVT_UCX_USBDEVICE_ADDRESS
---

# EVT_UCX_USBDEVICE_ADDRESS callback function


## -description

The client driver's implementation that UCX calls to address the USB device.

## -parameters

### -param UcxController [in]


 A handle to the UCX controller that the client driver received in a previous call to  the <a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

### -param Request [in]


A structure of type <a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_address">USBDEVICE_ADDRESS</a>.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples


```
VOID
UsbDevice_EvtUcxUsbDeviceAddress(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)

{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceAddress");

    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &wdfRequestParams);

    usbDeviceAddress = (PUSBDEVICE_ADDRESS)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdeviceinitseteventcallbacks">UcxUsbDeviceInitSetEventCallbacks</a>

