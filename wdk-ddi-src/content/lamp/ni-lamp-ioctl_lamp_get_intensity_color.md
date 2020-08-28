---
UID: NI:lamp.IOCTL_LAMP_GET_INTENSITY_COLOR
title: IOCTL_LAMP_GET_INTENSITY_COLOR (lamp.h)
description: The IOCTL_LAMP_GET_INTENSITY_COLOR control code queries the light intensity when the lamp is configured to emit color light.
old-location: stream\ioctl_lamp_get_intensity_color.htm
tech.root: stream
ms.assetid: 8BAAB861-677D-4945-92B7-BDBE7A29695E
ms.date: 04/23/2018
keywords: ["IOCTL_LAMP_GET_INTENSITY_COLOR IOCTL"]
ms.keywords: IOCTL_LAMP_GET_INTENSITY_COLOR, IOCTL_LAMP_GET_INTENSITY_COLOR control, IOCTL_LAMP_GET_INTENSITY_COLOR control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_INTENSITY_COLOR, stream.ioctl_lamp_get_intensity_color
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
 - IOCTL_LAMP_GET_INTENSITY_COLOR
 - lamp/IOCTL_LAMP_GET_INTENSITY_COLOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - lamp.h
api_name:
 - IOCTL_LAMP_GET_INTENSITY_COLOR
---

# IOCTL_LAMP_GET_INTENSITY_COLOR IOCTL


## -description

The **IOCTL_LAMP_GET_INTENSITY_COLOR** control code queries the light intensity when the lamp is configured to emit color light.

```cpp
#define IOCTL_LAMP_GET_INTENSITY_COLOR \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0006, METHOD_BUFFERED, FILE_ANY_ACCESS)
```

## -ioctlparameters

### -input-buffer

`Irp->AssociatedIrp.SystemBuffer` points to a [LAMP_INTENSITY_COLOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ns-lamp-lamp_intensity_color) structure.

### -input-buffer-length

Length of a [LAMP_INTENSITY_COLOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ns-lamp-lamp_intensity_color) structure.

### -output-buffer

`Irp->AssociatedIrp.SystemBuffer` is filled with the light intensity information.

### -output-buffer-length

`IO_STACK_LOCATION.Parameters.DeviceIoControl.OutputBufferLength` is the length of the buffer in bytes passed in the `Irp->AssociatedIrp.SystemBuffer` field.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The driver sets `Irp->IoStatus.Status` to **STATUS_SUCCESS** or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a error **STATUS_RESOURCE_IN_USE** via `Irp->IoStatus.Status`.

## -remarks

The payload type of this IOCTL is a [LAMP_INTENSITY_COLOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ns-lamp-lamp_intensity_color) structure.

