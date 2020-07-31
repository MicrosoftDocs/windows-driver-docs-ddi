---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_DISABLE
title: EVT_UCX_USBDEVICE_DISABLE (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to release controller resources associated with the device and its default endpoint.
old-location: buses\evt_ucx_usbdevice_disable.htm
tech.root: usbref
ms.assetid: 85aa1d5e-e660-4fd7-a58d-8d32bbd966f2
ms.date: 05/07/2018
keywords: ["EVT_UCX_USBDEVICE_DISABLE callback function"]
ms.keywords: EVT_UCX_USBDEVICE_DISABLE, EVT_UCX_USBDEVICE_DISABLE callback, EvtUcxUsbDeviceDisable, EvtUcxUsbDeviceDisable callback function [Buses], PEVT_UCX_USBDEVICE_DISABLE, PEVT_UCX_USBDEVICE_DISABLE callback function pointer [Buses], buses.evt_ucx_usbdevice_disable, ucxusbdevice/EvtUcxUsbDeviceDisable
f1_keywords:
 - "ucxusbdevice/PEVT_UCX_USBDEVICE_DISABLE"
 - "PEVT_UCX_USBDEVICE_DISABLE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ucxusbdevice.h
api_name:
- PEVT_UCX_USBDEVICE_DISABLE
targetos: Windows
req.typenames: 
---

# EVT_UCX_USBDEVICE_DISABLE callback function


## -description


The client driver's implementation that UCX calls to release controller resources associated with the device and its default endpoint.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param Request [in]

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_disable">USBDEVICE_DISABLE</a>.


## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

When the client driver has released controller resources, it completes the WDFREQUEST.  After completion, the only callback function that UCX  calls referencing this USB device is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_enable">EVT_UCX_USBDEVICE_ENABLE</a>.

  While the device is disabled, UCX does not schedule transfers
    for it.


To
    transition the device to the desired state, the host controller driver communicates with the hardware to complete the request.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
UsbDevice_EvtUcxUsbDeviceDisable(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)


{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceDisable");

    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &wdfRequestParams);
    usbDeviceDisable = (PUSBDEVICE_DISABLE)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>
 

 

