---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
title: IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING (usbfnioctl.h)
description: The class driver sends this request to register a USB string descriptor.
old-location: buses\ioctl_internal_usbfn_register_usb_string.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING, IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING control, IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING control code [Buses], buses.ioctl_internal_usbfn_register_usb_string, usbfnioctl/IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
req.header: usbfnioctl.h
req.include-header: 
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
 - IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
 - usbfnioctl/IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnioctl.h
api_name:
 - IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
---

# IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING IOCTL


## -description

The class driver sends this request to register a USB string descriptor.

## -ioctlparameters

### -input-buffer

A pointer to a buffer that contains a  <a href="/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_usb_string">USBFN_USB_STRING</a> structure with the USB string descriptor.

### -input-buffer-length

The length of the input buffer must be at least <code>sizeof(USBFN_USB_STRING)</code>.

### -output-buffer

NULL.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

This request must be sent after sending the <a href="/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a>



<a href="/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_usb_string">USBFN_USB_STRING</a>
