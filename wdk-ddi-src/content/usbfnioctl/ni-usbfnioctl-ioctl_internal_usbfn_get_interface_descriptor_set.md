---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET
title: IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET (usbfnioctl.h)
description: The class driver sends this request to get the entire USB interface descriptor set for a function on the device.
old-location: buses\ioctl_internal_usbfn_get_interface_descriptor_set_.htm
tech.root: usbref
ms.assetid: AF5E2559-151B-4176-A25E-6A1955747F1A
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET, IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET control, IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET control code [Buses], buses.ioctl_internal_usbfn_get_interface_descriptor_set_, usbfnioctl/IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET
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
 - IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET
 - usbfnioctl/IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnioctl.h
api_name:
 - IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET
---

# IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET IOCTL


## -description

The class driver sends this request to get the entire USB interface descriptor set for a function on the device.
<div class="alert"><b>Note</b>  Do not use this request to retrieve the interface descriptor set for the entire device.</div><div> </div>

## -ioctlparameters

### -input-buffer

A pointer to a buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_interface_info">USBFN_INTERFACE_INFO</a> structure.

### -input-buffer-length

The length of the input buffer must be at least <code>sizeof(USBFN_INTERFACE_INFO)</code>.

### -output-buffer

A pointer to a buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_interface_info">USBFN_INTERFACE_INFO</a> structure. USB function class extension (UFX) populates the structure with the entire interface descriptor set including its endpoint descriptors.

### -output-buffer-length

The length of the output buffer must be at least <code>sizeof(USBFN_INTERFACE_INFO)</code>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

This request must be sent after sending the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

The length of the entire interface descriptor is variable. The class driver might need to send this IOCTL request twice to get the entire descriptor set.

If the length of the entire descriptor set is greater than the  specified output buffer length, UFX sets the <b>Size</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_interface_info">USBFN_INTERFACE_INFO</a> to the actual buffer length and fails the request with STATUS_BUFFER_TOO_SMALL. The driver must then allocated an output buffer of length specified by <b>Size</b> and resend the request.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_interface_info">USBFN_INTERFACE_INFO</a>

