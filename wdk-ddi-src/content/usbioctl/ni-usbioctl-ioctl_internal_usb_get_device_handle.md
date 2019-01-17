---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE
title: IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE
description: The IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_get_device_handle.htm
tech.root: usbref
ms.assetid: 4c2c7b8b-4b4b-4a76-8dac-106c94f347c5
ms.date: 05/07/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE, IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE control, IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE control code [Buses], buses.ioctl_internal_usb_get_device_handle, usbioctl/IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE IOCTL


## -description


 The <b>IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE</b> IOCTL is used by the USB hub driver. Do not use.


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



