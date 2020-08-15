---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_RESET
title: EVT_UCX_USBDEVICE_RESET (ucxusbdevice.h)
description: The client driver's implementation that UCX calls when the port to which the device is attached is reset.
old-location: buses\evt_ucx_usbdevice_reset.htm
tech.root: usbref
ms.assetid: 6876e35c-f293-4849-915f-c686a9d91dd1
ms.date: 05/07/2018
keywords: ["EVT_UCX_USBDEVICE_RESET callback function"]
ms.keywords: EVT_UCX_USBDEVICE_RESET, EVT_UCX_USBDEVICE_RESET callback, EvtUcxUsbDeviceReset, EvtUcxUsbDeviceReset callback function [Buses], PEVT_UCX_USBDEVICE_RESET, PEVT_UCX_USBDEVICE_RESET callback function pointer [Buses], buses.evt_ucx_usbdevice_reset, ucxusbdevice/EvtUcxUsbDeviceReset
f1_keywords:
 - "ucxusbdevice/PEVT_UCX_USBDEVICE_RESET"
 - "PEVT_UCX_USBDEVICE_RESET"
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
- PEVT_UCX_USBDEVICE_RESET
targetos: Windows
req.typenames: 
---

# EVT_UCX_USBDEVICE_RESET callback function


## -description


The client driver's implementation that UCX calls when the port to which the device is
    attached is reset.


## -parameters




### -param UcxController 
[in]
 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param Request 
[in]
Contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_reset">USBDEVICE_RESET</a> structure.


## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

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
UsbDevice_EvtUcxUsbDeviceReset(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)

{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceReset");

    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &wdfRequestParams);
    usbDeviceReset = (PUSBDEVICE_RESET)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_reset">USBDEVICE_RESET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>
 

 

