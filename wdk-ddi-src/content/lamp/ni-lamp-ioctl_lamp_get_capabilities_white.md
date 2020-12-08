---
UID: NI:lamp.IOCTL_LAMP_GET_CAPABILITIES_WHITE
title: IOCTL_LAMP_GET_CAPABILITIES_WHITE (lamp.h)
description: The IOCTL_LAMP_GET_CAPABILITIES_WHITE control code queries the capabilities of the lamp when the device is configured to emit white light.
old-location: stream\ioctl_lamp_get_capabilities_white.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IOCTL_LAMP_GET_CAPABILITIES_WHITE IOCTL"]
ms.keywords: IOCTL_LAMP_GET_CAPABILITIES_WHITE, IOCTL_LAMP_GET_CAPABILITIES_WHITE control, IOCTL_LAMP_GET_CAPABILITIES_WHITE control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_CAPABILITIES_WHITE, stream.ioctl_lamp_get_capabilities_white
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_LAMP_GET_CAPABILITIES_WHITE
 - lamp/IOCTL_LAMP_GET_CAPABILITIES_WHITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - lamp.h
api_name:
 - IOCTL_LAMP_GET_CAPABILITIES_WHITE
---

# IOCTL_LAMP_GET_CAPABILITIES_WHITE IOCTL


## -description

The **IOCTL_LAMP_GET_CAPABILITIES_WHITE** control code queries the capabilities of the lamp when the device is configured to emit white light.

```cpp
#define IOCTL_LAMP_GET_CAPABILITIES_WHITE \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0000, METHOD_BUFFERED, FILE_ANY_ACCESS)
```

## -ioctlparameters

### -input-buffer

`Irp->AssociatedIrp.SystemBuffer` points to a buffer of type [LAMP_CAPABILITIES_WHITE](./ns-lamp-lamp_capabilities_white.md).

### -input-buffer-length

Length of the buffer.

### -output-buffer

`Irp->AssociatedIrp.SystemBuffer` is filled with all capabilities supported by the lamp hardware.

### -output-buffer-length

`IO_STACK_LOCATION.Parameters.DeviceIoControl.OutputBufferLength` is the length of the buffer (in bytes) passed in the `Irp->AssociatedIrp.SystemBuffer` field.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The driver sets `Irp->IoStatus.Status` to **STATUS_SUCCESS** or the appropriate error status. It will set `Irp->IoStatus.Information` to the number of bytes required to hold the buffer.

## -remarks

By requirement, a lamp whose driver supports the **GUID_DEVINTERFACE_LAMP** interface is required to support emitting white light.

The payload of this IOCTL is a [LAMP_CAPABILITIES_WHITE](./ns-lamp-lamp_capabilities_white.md) structure.

The **IsLightIntensityAdjustable** field indicates whether the luminance level can be programmed. If this field evaluates to **FALSE**, it means that the underlying device only supports the on/off switch and the light intensity cannot be adjusted.
