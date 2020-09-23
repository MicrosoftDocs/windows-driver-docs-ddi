---
UID: NF:usbdlib.UsbBuildGetStatusRequest
title: UsbBuildGetStatusRequest macro (usbdlib.h)
description: The UsbBuildGetStatusRequest macro formats an URB to obtain status from a device, interface, endpoint, or other device-defined target on a USB device.
old-location: buses\usbbuildgetstatusrequest.htm
tech.root: usbref
ms.assetid: 7a5fcb4f-fc9a-4ebb-93ef-b83461557b22
ms.date: 05/07/2018
keywords: ["UsbBuildGetStatusRequest macro"]
ms.keywords: UsbBuildGetStatusRequest, UsbBuildGetStatusRequest routine [Buses], buses.usbbuildgetstatusrequest, usbdlib/UsbBuildGetStatusRequest, usbfunc_a99bf737-8bb6-4000-af2b-ac076a4ffc8e.xml
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - UsbBuildGetStatusRequest
 - usbdlib/UsbBuildGetStatusRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbdlib.h
api_name:
 - UsbBuildGetStatusRequest
---

# UsbBuildGetStatusRequest macro


## -description

   The <b>UsbBuildGetStatusRequest</b> macro formats an <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> to obtain status from a device, interface, endpoint, or other device-defined target on a USB device.

## -parameters

### -param urb 

[in, out]
Pointer to an <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> to be formatted as an status request.

### -param op 

[in]
Specifies one of the following values:





#### URB_FUNCTION_GET_STATUS_FROM_DEVICE

Retrieves status from a USB device.



#### URB_FUNCTION_GET_STATUS_FROM_INTERFACE

Retrieves status from an interface on a USB device.



#### URB_FUNCTION_GET_STATUS_FROM_ENDPOINT

Retrieves status from an endpoint for an interface on a USB device.



#### URB_FUNCTION_GET_STATUS_FROM_OTHER

Retrieves status from a device-defined target on a USB device.

### -param index 

[in]
Specifies the device-defined index, returned by a successful configuration request, if the request is for an endpoint or interface. Otherwise, <i>Index</i> must be zero.

### -param transferBuffer 

[in, optional]
Pointer to a resident buffer to receive the status data or is <b>NULL</b> if an MDL is supplied in <i>TransferBufferMDL</i>.

### -param transferBufferMDL 

[in, optional]
Pointer to an MDL that describes a resident buffer to receive the status data or is <b>NULL</b> if a buffer is supplied in <i>TransferBuffer</i>.

### -param link 

[in]
Reserved. Must be set to <b>NULL</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="/windows-hardware/drivers/ddi/_usbref/">USB device driver programming reference</a>



<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_get_status_request">_URB_CONTROL_GET_STATUS_REQUEST</a>