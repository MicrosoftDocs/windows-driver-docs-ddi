---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
title: IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION (ntdd8042.h)
description: The IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION request passes a pointer to a mouse interrupt object.
old-location: hid\ioctl_internal_i8042_mouse_start_information.htm
tech.root: hid
ms.assetid: aa7d5802-d1d0-4c7c-bf55-0f0b5b664113
ms.date: 04/30/2018
keywords: ["IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION IOCTL"]
ms.keywords: IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION, IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION control, IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION control code [Human Input Devices], hid.ioctl_internal_i8042_mouse_start_information, i8042ref_c4c81870-f104-4979-86e3-03bd376e34ce.xml, ntdd8042/IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
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
 - IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
 - ntdd8042/IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdd8042.h
api_name:
 - IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION
---

# IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION IOCTL


## -description

The IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION request passes a pointer to a mouse interrupt object. I8042prt sends this request synchronously to the top of the device stack after the mouse interrupt object is created. Upper-level filter drivers that need to synchronize their callback operation with the mouse ISR can use the pointer to the mouse interrupt object.

## -ioctlparameters

### -input-buffer

<b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to an input buffer allocated by I8042prt to input an <a href="/windows-hardware/drivers/ddi/ntdd8042/ns-ntdd8042-_internal_i8042_start_information">INTERNAL_I8042_START_INFORMATION</a> structure.

### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> specifies the size, in bytes, of an INTERNAL_I8042_START_INFORMATION structure.

### -output-buffer

None

### -output-buffer-length

None

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to STATUS_SUCCESS.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdd8042/ns-ntdd8042-_internal_i8042_start_information">INTERNAL_I8042_START_INFORMATION</a>