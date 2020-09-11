---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ENABLE
title: EVT_UCX_USBDEVICE_ENABLE (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to program information about the device and its default control endpoint into the controller.
old-location: buses\evt_ucx_usbdevice_enable.htm
tech.root: usbref
ms.assetid: ac46a6eb-c30d-4b1f-8e14-0ae44ae0d4f1
ms.date: 05/07/2018
keywords: ["EVT_UCX_USBDEVICE_ENABLE callback function"]
ms.keywords: EVT_UCX_USBDEVICE_ENABLE, EVT_UCX_USBDEVICE_ENABLE callback, EvtUcxUsbDeviceEnable, EvtUcxUsbDeviceEnable callback function [Buses], PEVT_UCX_USBDEVICE_ENABLE, PEVT_UCX_USBDEVICE_ENABLE callback function pointer [Buses], buses.evt_ucx_usbdevice_enable, ucxusbdevice/EvtUcxUsbDeviceEnable
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
 - EVT_UCX_USBDEVICE_ENABLE
 - ucxusbdevice/EVT_UCX_USBDEVICE_ENABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxusbdevice.h
api_name:
 - PEVT_UCX_USBDEVICE_ENABLE
---

# EVT_UCX_USBDEVICE_ENABLE callback function


## -description

The client driver's implementation that UCX calls to program information about the device and its default control endpoint
    into the controller.

## -parameters

### -param UcxController 

[in]
 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

### -param Request 

[in]
A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_enable">USBDEVICE_ENABLE</a>.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

To
    transition the device to the desired state, the host controller driver communicates with the hardware to complete the request.

In this callback function, the client driver prepares the controller to accept and schedule transfers on the default control
    endpoint for the USB device.

When the driver has finished, it completes the WDFREQUEST.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples


```
VOID
UsbDevice_EvtUcxUsbDeviceEnable(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)
    
{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceEnable");

    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &wdfRequestParams);
    usbDeviceEnable = (PUSBDEVICE_ENABLE)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}
```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>

