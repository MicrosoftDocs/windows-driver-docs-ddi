---
UID: NS:usb._URB_GET_CURRENT_FRAME_NUMBER
title: _URB_GET_CURRENT_FRAME_NUMBER (usb.h)
description: The _URB_GET_CURRENT_FRAME_NUMBER structure is used by USB client drivers to retrieve the current frame number.
old-location: buses\_urb_get_current_frame_number.htm
tech.root: usbref
ms.assetid: 4c6e5064-83b4-4d3c-ab08-041070128f3c
ms.date: 05/07/2018
keywords: ["URB_GET_CURRENT_FRAME_NUMBER structure"]
ms.keywords: "_URB_GET_CURRENT_FRAME_NUMBER, _URB_GET_CURRENT_FRAME_NUMBER structure [Buses], buses._urb_get_current_frame_number, usb/_URB_GET_CURRENT_FRAME_NUMBER, usbstrct_b767de1b-63fd-4ac4-b696-78e4d0d83661.xml"
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
targetos: Windows
req.typenames: 
f1_keywords:
 - _URB_GET_CURRENT_FRAME_NUMBER
 - usb/_URB_GET_CURRENT_FRAME_NUMBER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usb.h
api_name:
 - _URB_GET_CURRENT_FRAME_NUMBER
---

# _URB_GET_CURRENT_FRAME_NUMBER structure


## -description

The <b>_URB_GET_CURRENT_FRAME_NUMBER</b> structure is used by USB client drivers to retrieve the current frame number.

## -struct-fields

### -field Hdr

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_GET_CURRENT_FRAME_NUMBER, and <b>Hdr.Length</b> must be <code>sizeof(_URB_GET_CURRENT_FRAME_NUMBER)</code>.

### -field FrameNumber

Contains the current 32-bit frame number, on the USB bus, on return from the host controller driver.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a>

