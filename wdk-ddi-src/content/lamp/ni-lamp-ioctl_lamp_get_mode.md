---
UID: NI:lamp.IOCTL_LAMP_GET_MODE
title: IOCTL_LAMP_GET_MODE (lamp.h)
description: The IOCTL_LAMP_GET_MODE control code queries the mode with which the lamp is currently configured.
old-location: stream\ioctl_lamp_get_mode.htm
tech.root: stream
ms.assetid: 741FFB14-B6F1-452B-AD8A-E82C0E34CB6A
ms.date: 04/23/2018
ms.keywords: IOCTL_LAMP_GET_MODE, IOCTL_LAMP_GET_MODE control, IOCTL_LAMP_GET_MODE control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_MODE, stream.ioctl_lamp_get_mode
f1_keywords:
 - "lamp/IOCTL_LAMP_GET_MODE"
req.header: lamp.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- lamp.h
api_name:
- IOCTL_LAMP_GET_MODE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_GET_MODE IOCTL

## -description

The **IOCTL_LAMP_GET_MODE** control code queries the mode with which the lamp is currently configured.

```cpp
#define IOCTL_LAMP_GET_MODE \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0002, METHOD_BUFFERED, FILE_ANY_ACCESS)
```

## -ioctlparameters

### -input-buffer

`Irp->AssociatedIrp.SystemBuffer` points to a buffer of type [LAMP_MODE](https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ne-lamp-lamp_mode).

### -input-buffer-length

Length of [LAMP_MODE](https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ne-lamp-lamp_mode).

### -output-buffer

`Irp->AssociatedIrp.SystemBuffer` is filled with a **LAMP_MODE** value.

### -output-buffer-length

`IO_STACK_LOCATION.Parameters.DeviceIoControl.OutputBufferLength` is the length of the buffer in bytes passed in the `Irp->AssociatedIrp.SystemBuffer` field.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The driver sets `Irp->IoStatus.Status` to **STATUS_SUCCESS** or the appropriate error status. It will set `Irp->IoStatus.Information` to the number of bytes required to hold a **DWORD** value.

If the device has been acquired by a camera driver, the lamp driver should return a **STATUS_RESOURCE_IN_USE** error via `Irp->IoStatus.Status`.
