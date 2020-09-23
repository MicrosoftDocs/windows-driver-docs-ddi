---
UID: NI:usbioctl.IOCTL_USB_HCD_DISABLE_PORT
title: IOCTL_USB_HCD_DISABLE_PORT (usbioctl.h)
description: The IOCTL_USB_HCD_DISABLE_PORT IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_usb_hcd_disable_port.htm
tech.root: usbref
ms.assetid: c0ae41be-1b37-4410-8e7a-611a66c599c1
ms.date: 05/07/2018
keywords: ["IOCTL_USB_HCD_DISABLE_PORT IOCTL"]
ms.keywords: IOCTL_USB_HCD_DISABLE_PORT, IOCTL_USB_HCD_DISABLE_PORT control, IOCTL_USB_HCD_DISABLE_PORT control code [Buses], buses.ioctl_usb_hcd_disable_port, usbioctl/IOCTL_USB_HCD_DISABLE_PORT, usbirp_558a0a61-e35f-4015-9f72-df33e85c8c59.xml
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows Server 2003, Windows XP, and Windows 2000, but it is not available on Windows Vista.
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
 - IOCTL_USB_HCD_DISABLE_PORT
 - usbioctl/IOCTL_USB_HCD_DISABLE_PORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_USB_HCD_DISABLE_PORT
---

# IOCTL_USB_HCD_DISABLE_PORT IOCTL


## -description

The <b>IOCTL_USB_HCD_DISABLE_PORT</b> IOCTL has been deprecated. Do not use.

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