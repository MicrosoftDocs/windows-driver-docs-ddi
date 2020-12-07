---
UID: NI:usbioctl.IOCTL_USB_DIAG_IGNORE_HUBS_ON
title: IOCTL_USB_DIAG_IGNORE_HUBS_ON (usbioctl.h)
description: The IOCTL_USB_DIAG_IGNORE_HUBS_ON I/O control has been deprecated. Do not use.
old-location: buses\ioctl_usb_diag_ignore_hubs_on.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_USB_DIAG_IGNORE_HUBS_ON IOCTL"]
ms.keywords: IOCTL_USB_DIAG_IGNORE_HUBS_ON, IOCTL_USB_DIAG_IGNORE_HUBS_ON control, IOCTL_USB_DIAG_IGNORE_HUBS_ON control code [Buses], buses.ioctl_usb_diag_ignore_hubs_on, usbioctl/IOCTL_USB_DIAG_IGNORE_HUBS_ON, usbirp_7e95e023-3bb1-423d-b233-b5028e9af76b.xml
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Supported on Microsoft Windows 2000 only.
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
 - IOCTL_USB_DIAG_IGNORE_HUBS_ON
 - usbioctl/IOCTL_USB_DIAG_IGNORE_HUBS_ON
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_USB_DIAG_IGNORE_HUBS_ON
---

# IOCTL_USB_DIAG_IGNORE_HUBS_ON IOCTL


## -description

The <b>IOCTL_USB_DIAG_IGNORE_HUBS_ON</b> I/O control has been deprecated. Do not use.

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
