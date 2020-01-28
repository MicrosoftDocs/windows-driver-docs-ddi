---
UID: NS:usb._URB_CONTROL_GET_STATUS_REQUEST
title: _URB_CONTROL_GET_STATUS_REQUEST (usb.h)
description: The _URB_CONTROL_GET_STATUS_REQUEST structure is used by USB client drivers to retrieve status from a device, interface, endpoint, or other device-defined target.
old-location: buses\_urb_control_get_status_request.htm
tech.root: usbref
ms.assetid: 6a005ff3-951f-462d-84e6-e1fd931c5afc
ms.date: 05/07/2018
ms.keywords: "_URB_CONTROL_GET_STATUS_REQUEST, _URB_CONTROL_GET_STATUS_REQUEST structure [Buses], buses._urb_control_get_status_request, usb/_URB_CONTROL_GET_STATUS_REQUEST, usbstrct_b91864c5-b19a-492d-a5dc-1fabdf4c37f9.xml"
f1_keywords:
 - "usb/_URB_CONTROL_GET_STATUS_REQUEST"
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usb.h
api_name:
- _URB_CONTROL_GET_STATUS_REQUEST
product:
- Windows
targetos: Windows
req.typenames: 
---

# _URB_CONTROL_GET_STATUS_REQUEST structure


## -description


The _URB_CONTROL_GET_STATUS_REQUEST structure is used by USB client drivers to retrieve status from a device, interface, endpoint, or other device-defined target.


## -struct-fields




### -field Hdr

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Length</b> must be <code>sizeof(_URB_CONTROL_GET_STATUS_REQUEST)</code>, and <b>Hdr.Function</b> must be one of the following values:

* URB_FUNCTION_GET_STATUS_FROM_DEVICE
* URB_FUNCTION_GET_STATUS_FROM_INTERFACE
* URB_FUNCTION_GET_STATUS_FROM_ENDPOINT
* URB_FUNCTION_GET_STATUS_FROM_OTHER


### -field Reserved

Reserved. Do not use.


### -field Reserved0

Reserved. Do not use.


### -field TransferBufferLength

Must be 2. This member specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.


### -field TransferBuffer

Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. The bus driver returns a single byte specifying the status for the target.  


### -field TransferBufferMDL

Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. The bus driver returns a single byte specifying the status for the target. This MDL must be allocated from nonpaged pool.


### -field UrbLink

Reserved. Do not use.


### -field hca

Reserved. Do not use.


### -field Reserved1

Reserved. Do not use.


### -field Index

Specifies the device-defined index, returned by a successful configuration request, if the request is for an endpoint or interface. Otherwise, <b>Index</b> must be zero.


### -field Reserved2

Reserved. Do not use.


## -remarks



Drivers can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbbuildgetstatusrequest">UsbBuildGetStatusRequest</a> service routine to format this URB.

The reserved members of this structure must be treated as opaque and are reserved for system use.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a>
 

 

