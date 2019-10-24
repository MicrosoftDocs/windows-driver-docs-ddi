---
UID: NI:lamp.IOCTL_LAMP_GET_CAPABILITIES_COLOR
title: IOCTL_LAMP_GET_CAPABILITIES_COLOR (lamp.h)
description: The IOCTL_LAMP_GET_CAPABILITIES_COLOR control code queries the capabilities of the lamp when the device is configured to emit color light.
old-location: stream\ioctl_lamp_get_capabilities_color.htm
tech.root: stream
ms.assetid: CC7B1824-E397-414A-8EB6-130AEC031304
ms.date: 04/23/2018
ms.keywords: IOCTL_LAMP_GET_CAPABILITIES_COLOR, IOCTL_LAMP_GET_CAPABILITIES_COLOR control, IOCTL_LAMP_GET_CAPABILITIES_COLOR control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_CAPABILITIES_COLOR, stream.ioctl_lamp_get_capabilities_color
ms.topic: ioctl
f1_keywords:
 - "lamp/IOCTL_LAMP_GET_CAPABILITIES_COLOR"
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
- IOCTL_LAMP_GET_CAPABILITIES_COLOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_GET_CAPABILITIES_COLOR IOCTL

## -description

The **IOCTL_LAMP_GET_CAPABILITIES_COLOR** control code queries the capabilities of the lamp when the device is configured to emit color light.

```cpp
#define IOCTL_LAMP_GET_CAPABILITIES_COLOR \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0001, METHOD_BUFFERED, FILE_ANY_ACCESS)
```

## -ioctlparameters

### -input-buffer

`Irp->AssociatedIrp.SystemBuffer` points to a buffer of type [LAMP_CAPABILITIES_COLOR](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/lamp/ns-lamp-lamp_capabilities_color).


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

The payload of this IOCTL is a [LAMP_CAPABILITIES_COLOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ns-lamp-lamp_capabilities_color) structure.

The **IsSupported** field indicates whether the lamp can emit color light. If the hardware does not support color light, the driver should set this field to **FALSE**.

The **IsLightIntensityAdjustable** field indicates whether the luminance level can be programmed. If the lamp does not support color light (**IsSupported** evaluates to **FALSE**), a client should discard the value of **IsLightIntensityAdjustable**.
