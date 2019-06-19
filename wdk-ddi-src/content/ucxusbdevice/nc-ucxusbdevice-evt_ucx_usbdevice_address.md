---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ADDRESS
title: EVT_UCX_USBDEVICE_ADDRESS (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to address the USB device.
old-location: buses\evt_ucx_usbdevice_address.htm
tech.root: usbref
ms.assetid: 48bda241-18b0-44c2-8e8b-7d3ecaad8a05
ms.date: 05/07/2018
ms.keywords: EVT_UCX_USBDEVICE_ADDRESS, EVT_UCX_USBDEVICE_ADDRESS callback, EvtUcxUsbDeviceAddress, EvtUcxUsbDeviceAddress callback function [Buses], PEVT_UCX_USBDEVICE_ADDRESS, PEVT_UCX_USBDEVICE_ADDRESS callback function pointer [Buses], buses.evt_ucx_usbdevice_address, ucxusbdevice/EvtUcxUsbDeviceAddress
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ucxusbdevice.h
api_name:
- PEVT_UCX_USBDEVICE_ADDRESS
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_USBDEVICE_ADDRESS callback function


## -description


The client driver's implementation that UCX calls to address the USB device.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param Request [in]

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/mt188070">USBDEVICE_ADDRESS</a>.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a> method.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
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
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188068">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188053">UcxUsbDeviceInitSetEventCallbacks</a>
 

 

