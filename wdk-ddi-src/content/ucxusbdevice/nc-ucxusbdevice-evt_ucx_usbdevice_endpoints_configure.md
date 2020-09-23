---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
title: EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to configure endpoints in the controller.
old-location: buses\evt_ucx_usbdevice_endpoints_configure.htm
tech.root: usbref
ms.assetid: 2f374912-985d-47e0-9fda-b43242375cb5
ms.date: 05/07/2018
keywords: ["EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function"]
ms.keywords: EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE, EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback, EvtUcxUsbDeviceEndpointsConfigure, EvtUcxUsbDeviceEndpointsConfigure callback function [Buses], PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE, PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function pointer [Buses], buses.evt_ucx_usbdevice_endpoints_configure, ucxusbdevice/EvtUcxUsbDeviceEndpointsConfigure
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
 - EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
 - ucxusbdevice/EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxusbdevice.h
api_name:
 - PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
---

# EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function


## -description

The client driver's implementation that UCX calls to configure endpoints in the controller.

## -parameters

### -param UcxController 

[in]
 A handle to the UCX controller that the client driver received in a previous call to  the <a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

### -param Request 

[in]
Contains a structure of type <a href="/windows-hardware/drivers/ddi/ucxendpoint/ns-ucxendpoint-_endpoints_configure">ENDPOINTS_CONFIGURE</a> structure.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

In the callback, the driver programs or deprograms the endpoints, as described in the <a href="/windows-hardware/drivers/ddi/ucxendpoint/ns-ucxendpoint-_endpoints_configure">ENDPOINTS_CONFIGURE</a> structure.

This callback does not enable or disable the default endpoint. The default endpoint’s state is tied to the state of the device.   The driver implements enable and disable operations in the <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_disable">EVT_UCX_USBDEVICE_DISABLE</a> and <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_enable">EVT_UCX_USBDEVICE_ENABLE</a> callback functions.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples


```
VOID
UsbDevice_EvtUcxUsbDeviceEndpointsConfigure(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)

{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceEndpointsConfigure");

    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &wdfRequestParams);

    ...

    endpointsConfigure = (PENDPOINTS_CONFIGURE)wdfRequestParams.Parameters.Others.Arg1;

    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}
```


## -see-also

<a href="/windows-hardware/drivers/ddi/ucxendpoint/ns-ucxendpoint-_endpoints_configure">ENDPOINTS_CONFIGURE</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>