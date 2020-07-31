---
UID: NI:lamp.IOCTL_LAMP_SET_INTENSITY_COLOR
title: IOCTL_LAMP_SET_INTENSITY_COLOR (lamp.h)
description: The IOCTL_LAMP_SET_INTENSITY_COLOR control code sets the lamp to the specified light intensity.
old-location: stream\ioctl_lamp_set_intensity_color.htm
tech.root: stream
ms.assetid: AD531C16-0E24-4CDE-B188-981260CF8F49
ms.date: 04/23/2018
keywords: ["IOCTL_LAMP_SET_INTENSITY_COLOR IOCTL"]
ms.keywords: IOCTL_LAMP_SET_INTENSITY_COLOR, IOCTL_LAMP_SET_INTENSITY_COLOR control, IOCTL_LAMP_SET_INTENSITY_COLOR control code [Streaming Media Devices], lamp/IOCTL_LAMP_SET_INTENSITY_COLOR, stream.ioctl_lamp_set_intensity_color
f1_keywords:
 - "lamp/IOCTL_LAMP_SET_INTENSITY_COLOR"
 - "IOCTL_LAMP_SET_INTENSITY_COLOR"
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
- IOCTL_LAMP_SET_INTENSITY_COLOR
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_SET_INTENSITY_COLOR IOCTL

## -description

The **IOCTL_LAMP_SET_INTENSITY_COLOR** control code sets the lamp to the specified light intensity.

```cpp
#define IOCTL_LAMP_SET_INTENSITY_COLOR \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0007, METHOD_BUFFERED, FILE_ANY_ACCESS)
```

## -ioctlparameters

### -input-buffer

`Irp->AssociatedIrp.SystemBuffer` points to a [LAMP_INTENSITY_COLOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ns-lamp-lamp_intensity_color) structure.

### -input-buffer-length

Length of a [LAMP_INTENSITY_COLOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ns-lamp-lamp_intensity_color) structure.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The driver sets `Irp->IoStatus.Status` to **STATUS_SUCCESS** or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a **STATUS_RESOURCE_IN_USE** error via `Irp->IoStatus.Status`.
