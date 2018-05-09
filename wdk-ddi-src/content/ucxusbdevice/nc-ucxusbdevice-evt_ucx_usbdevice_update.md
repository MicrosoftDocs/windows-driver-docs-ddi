---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_UPDATE
title: EVT_UCX_USBDEVICE_UPDATE
author: windows-driver-content
description: The client driver's implementation that UCX calls to update device properties.
old-location: buses\evt_ucx_usbdevice_update.htm
old-project: usbref
ms.assetid: 5dbf3560-9968-4996-8bce-fb43e3918d72
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: EVT_UCX_USBDEVICE_UPDATE, EVT_UCX_USBDEVICE_UPDATE callback, EvtUcxUsbDeviceUpdate, EvtUcxUsbDeviceUpdate callback function [Buses], PEVT_UCX_USBDEVICE_UPDATE, PEVT_UCX_USBDEVICE_UPDATE callback function pointer [Buses], buses.evt_ucx_usbdevice_update, ucxusbdevice/EvtUcxUsbDeviceUpdate
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
-	PEVT_UCX_USBDEVICE_UPDATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_USBDEVICE_UPDATE callback function


## -description


The client driver's implementation that UCX calls to
    update device properties.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param Request [in]

Contains the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188080">USBDEVICE_UPDATE</a> structure.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a> method.

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

    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &amp;wdfRequestParams);
    usbDeviceUpdate = (PUSBDEVICE_UPDATE)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188068">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188080">USBDEVICE_UPDATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188053">UcxUsbDeviceInitSetEventCallbacks</a>
 

 

