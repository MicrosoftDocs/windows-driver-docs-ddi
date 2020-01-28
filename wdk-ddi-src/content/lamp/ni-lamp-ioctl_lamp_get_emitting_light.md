---
UID: NI:lamp.IOCTL_LAMP_GET_EMITTING_LIGHT
title: IOCTL_LAMP_GET_EMITTING_LIGHT (lamp.h)
description: The IOCTL_LAMP_GET_EMITTING_LIGHT control code queries if the lamp is turned on.
old-location: stream\ioctl_lamp_get_emitting_light.htm
tech.root: stream
ms.assetid: 82BBD72D-9F65-442F-8B25-E80A2160C5A2
ms.date: 04/23/2018
ms.keywords: IOCTL_LAMP_GET_EMITTING_LIGHT, IOCTL_LAMP_GET_EMITTING_LIGHT control, IOCTL_LAMP_GET_EMITTING_LIGHT control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_EMITTING_LIGHT, stream.ioctl_lamp_get_emitting_light
f1_keywords:
 - "lamp/IOCTL_LAMP_GET_EMITTING_LIGHT"
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
- IOCTL_LAMP_GET_EMITTING_LIGHT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_GET_EMITTING_LIGHT IOCTL

## -description

The **IOCTL_LAMP_GET_EMITTING_LIGHT** control code queries if the lamp is turned on.

```cpp
#define IOCTL_LAMP_GET_EMITTING_LIGHT \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0008, METHOD_BUFFERED, FILE_ANY_ACCESS)
```

## -ioctlparameters

### -input-buffer

`Irp->AssociatedIrp.SystemBuffer` points to a buffer of type **BOOLEAN**.

### -input-buffer-length

Length of a **BOOLEAN**.

### -output-buffer

`Irp->AssociatedIrp.SystemBuffer` contains the lamp state; **TRUE** if the lamp is turned on and emitting light; **FALSE** otherwise.

### -output-buffer-length

`IO_STACK_LOCATION.Parameters.DeviceIoControl.OutputBufferLength` is the length of the buffer in bytes passed in the `Irp->AssociatedIrp.SystemBuffer` field.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The driver sets `Irp->IoStatus.Status` to **STATUS_SUCCESS** or the appropriate error status. It will set `Irp->IoStatus.Information` to the number of bytes required to hold a **DWORD** value.

If the device has been acquired by a camera driver, the lamp driver should return a **STATUS_RESOURCE_IN_USE** error via `Irp->IoStatus.Status`.
