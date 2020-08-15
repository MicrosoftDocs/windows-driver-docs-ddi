---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_UPDATE
title: EVT_UCX_USBDEVICE_UPDATE (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to update device properties.
old-location: buses\evt_ucx_usbdevice_update.htm
tech.root: usbref
ms.assetid: 5dbf3560-9968-4996-8bce-fb43e3918d72
ms.date: 05/07/2018
keywords: ["EVT_UCX_USBDEVICE_UPDATE callback function"]
ms.keywords: EVT_UCX_USBDEVICE_UPDATE, EVT_UCX_USBDEVICE_UPDATE callback, EvtUcxUsbDeviceUpdate, EvtUcxUsbDeviceUpdate callback function [Buses], PEVT_UCX_USBDEVICE_UPDATE, PEVT_UCX_USBDEVICE_UPDATE callback function pointer [Buses], buses.evt_ucx_usbdevice_update, ucxusbdevice/EvtUcxUsbDeviceUpdate
f1_keywords:
 - "ucxusbdevice/PEVT_UCX_USBDEVICE_UPDATE"
 - "PEVT_UCX_USBDEVICE_UPDATE"
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
- PEVT_UCX_USBDEVICE_UPDATE
targetos: Windows
req.typenames: 
---

# EVT_UCX_USBDEVICE_UPDATE callback function


## -description


The client driver's implementation that UCX calls to
    update device properties.


## -parameters




### -param UcxController 
[in]
 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param Request 
[in]
Contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update">USBDEVICE_UPDATE</a> structure.


## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

The host controller driver communicates with the hardware to update descriptors, LPM parameters, whether device is a hub, and
    maximum exit latency, as needed.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
UsbDevice_EvtUcxUsbDeviceUpdate(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)

{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceUpdate");

    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &wdfRequestParams);
    usbDeviceUpdate = (PUSBDEVICE_UPDATE)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update">USBDEVICE_UPDATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdeviceinitseteventcallbacks">UcxUsbDeviceInitSetEventCallbacks</a>
 

 

