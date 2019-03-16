---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX
title: IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX (usbioctl.h)
description: The IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_get_device_handle_ex.htm
tech.root: usbref
ms.assetid: 76b89f35-4751-4eda-88f7-69f1a9835bbb
ms.date: 05/07/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX, IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX control, IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX control code [Buses], buses.ioctl_internal_usb_get_device_handle_ex, usbioctl/IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later operating systems.
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
- Usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX IOCTL


## -description


 The <b>IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX</b> IOCTL is used by the USB hub driver. Do not use.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).



