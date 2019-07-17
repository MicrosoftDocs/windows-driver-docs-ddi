---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_HUB_INFO
title: EVT_UCX_USBDEVICE_HUB_INFO (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to retrieve hub properties.
old-location: buses\evt_ucx_usbdevice_hub_info.htm
tech.root: usbref
ms.assetid: 5bf8000d-63d8-4901-b3fc-d3c43cefe37e
ms.date: 05/07/2018
ms.keywords: EVT_UCX_USBDEVICE_HUB_INFO, EVT_UCX_USBDEVICE_HUB_INFO callback, EvtUcxUsbDeviceHubInfo, EvtUcxUsbDeviceHubInfo callback function [Buses], PEVT_UCX_USBDEVICE_HUB_INFO, PEVT_UCX_USBDEVICE_HUB_INFO callback function pointer [Buses], buses.evt_ucx_usbdevice_hub_info, ucxusbdevice/EvtUcxUsbDeviceHubInfo
ms.topic: callback
f1_keywords:
 - "ucxusbdevice/PEVT_UCX_USBDEVICE_HUB_INFO"
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
- PEVT_UCX_USBDEVICE_HUB_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_USBDEVICE_HUB_INFO callback function


## -description


The client driver's implementation that UCX calls to
retrieve hub properties.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param Request [in]

Contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/ns-ucxusbdevice-_usbdevice_hub_info">USBDEVICE_HUB_INFO</a> structure.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

If the USB device is not a hub, do not provide this callback.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
UsbDevice_EvtUcxUsbDeviceHubInfo(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)

{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceHubInfo");

    //
    // Retrieve the USBDEVICE_HUB_INFO pointer from the
    // IOCTL_INTERNAL_USB_USBDEVICE_HUB_INFO WdfRequest.
    //
    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &wdfRequestParams);

    hubInfo = (PUSBDEVICE_HUB_INFO)wdfRequestParams.Parameters.Others.Arg1;

    ....


    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/ns-ucxusbdevice-_ucx_usbdevice_event_callbacks">UCX_USBDEVICE_EVENT_CALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/ns-ucxusbdevice-_usbdevice_hub_info">USBDEVICE_HUB_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>
 

 

