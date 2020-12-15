---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_RESERVED
title: IOCTL_INTERNAL_USBFN_RESERVED (usbfnioctl.h)
description: Do not use.
old-location: buses\ioctl_internal_usbfn_reserved.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_RESERVED IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_RESERVED, IOCTL_INTERNAL_USBFN_RESERVED control, IOCTL_INTERNAL_USBFN_RESERVED control code [Buses], buses.ioctl_internal_usbfn_reserved, usbfnioctl/IOCTL_INTERNAL_USBFN_RESERVED
req.header: usbfnioctl.h
req.include-header: Usbfnioctl.h
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
 - IOCTL_INTERNAL_USBFN_RESERVED
 - usbfnioctl/IOCTL_INTERNAL_USBFN_RESERVED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnioctl.h
api_name:
 - IOCTL_INTERNAL_USBFN_RESERVED
---

# IOCTL_INTERNAL_USBFN_RESERVED IOCTL


## -description

Do not use.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).
