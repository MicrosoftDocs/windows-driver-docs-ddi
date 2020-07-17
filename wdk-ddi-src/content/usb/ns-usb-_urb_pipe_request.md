---
UID: NS:usb._URB_PIPE_REQUEST
title: _URB_PIPE_REQUEST (usb.h)
description: The _URB_PIPE_REQUEST structure is used by USB client drivers to clear a stall condition on an endpoint.
old-location: buses\_urb_pipe_request.htm
tech.root: usbref
ms.assetid: 611bddf9-befd-4d2f-8e7d-7b5fe0744c03
ms.date: 05/07/2018
keywords: ["_URB_PIPE_REQUEST structure"]
ms.keywords: "_URB_PIPE_REQUEST, _URB_PIPE_REQUEST structure [Buses], buses._urb_pipe_request, usb/_URB_PIPE_REQUEST, usbstrct_dfcdbce6-e230-46a8-88df-59a253e6bfa0.xml"
f1_keywords:
 - "usb/_URB_PIPE_REQUEST"
 - "_URB_PIPE_REQUEST"
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
- _URB_PIPE_REQUEST
product:
- Windows
targetos: Windows
req.typenames: 
---

# _URB_PIPE_REQUEST structure


## -description


The <b>_URB_PIPE_REQUEST</b> structure is used by USB client drivers to clear a stall condition on an endpoint.


## -struct-fields




### -field Hdr

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be one of the following: 

<ul>
<li>URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL</li>
<li>URB_FUNCTION_SYNC_RESET_PIPE</li>
<li>URB_FUNCTION_SYNC_CLEAR_STALL</li>
<li>URB_FUNCTION_ABORT_PIPE</li>
<li>URB_FUNCTION_CLOSE_STATIC_STREAMS</li>
</ul>
 The <b>Hdr.Length</b> member must be <code>sizeof(_URB_PIPE_REQUEST)</code>.


### -field PipeHandle

Specifies an opaque handle to the bulk or interrupt pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.


### -field Reserved

Reserved. Do not use.


## -remarks



The reserved members of this structure must be treated as opaque and are reserved for system use.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a>
 

 

