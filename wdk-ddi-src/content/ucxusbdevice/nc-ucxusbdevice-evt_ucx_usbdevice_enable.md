---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ENABLE
title: EVT_UCX_USBDEVICE_ENABLE
author: windows-driver-content
description: The client driver's implementation that UCX calls to program information about the device and its default control endpoint into the controller.
old-location: buses\evt_ucx_usbdevice_enable.htm
old-project: usbref
ms.assetid: ac46a6eb-c30d-4b1f-8e14-0ae44ae0d4f1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UCX_USBDEVICE_ENABLE, EvtUcxUsbDeviceEnable, EvtUcxUsbDeviceEnable callback function [Buses], PEVT_UCX_USBDEVICE_ENABLE, PEVT_UCX_USBDEVICE_ENABLE callback function pointer [Buses], buses.evt_ucx_usbdevice_enable, ucxusbdevice/EvtUcxUsbDeviceEnable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ucxusbdevice.h
api_name:
-	PEVT_UCX_USBDEVICE_ENABLE
product: Windows
targetos: Windows
req.typenames: STREAM_INFO, *PSTREAM_INFO
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_ENABLE callback


## -description


The client driver's implementation that UCX calls to program information about the device and its default control endpoint
    into the controller.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param Request [in]

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/mt188072">USBDEVICE_ENABLE</a>.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a> method.

To
    transition the device to the desired state, the host controller driver communicates with the hardware to complete the request.

In this callback function, the client driver prepares the controller to accept and schedule transfers on the default control
    endpoint for the USB device.

When the driver has finished, it completes the WDFREQUEST.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
UsbDevice_EvtUcxUsbDeviceEnable(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)
    
{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceEnable");

    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &amp;wdfRequestParams);
    usbDeviceEnable = (PUSBDEVICE_ENABLE)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a>
 

 

