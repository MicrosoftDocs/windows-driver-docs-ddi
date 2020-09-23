---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO
title: IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO (usbioctl.h)
description: The IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_get_roothub_pdo.htm
tech.root: usbref
ms.assetid: 57a0063d-1dc9-48ff-98e8-59a562cc5ce0
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO, IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO control, IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO control code [Buses], buses.ioctl_internal_usb_get_roothub_pdo, usbioctl/IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO, usbirp_66fee324-5309-4242-ad55-b0ed76dbf68e.xml
req.header: usbioctl.h
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
 - IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO
 - usbioctl/IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO
---

# IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO IOCTL


## -description

 The <b>IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO</b> IOCTL is used by the USB hub driver. Do not use.

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

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).