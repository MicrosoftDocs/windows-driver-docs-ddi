---
UID: NI:lamp.IOCTL_LAMP_SET_INTENSITY_WHITE
title: IOCTL_LAMP_SET_INTENSITY_WHITE (lamp.h)
description: The IOCTL_LAMP_SET_INTENSITY_WHITE control code sets the lamp to the specified light intensity.
old-location: stream\ioctl_lamp_set_intensity_white.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IOCTL_LAMP_SET_INTENSITY_WHITE IOCTL"]
ms.keywords: IOCTL_LAMP_SET_INTENSITY_WHITE, IOCTL_LAMP_SET_INTENSITY_WHITE control, IOCTL_LAMP_SET_INTENSITY_WHITE control code [Streaming Media Devices], lamp/IOCTL_LAMP_SET_INTENSITY_WHITE, stream.ioctl_lamp_set_intensity_white
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
 - IOCTL_LAMP_SET_INTENSITY_WHITE
 - lamp/IOCTL_LAMP_SET_INTENSITY_WHITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - lamp.h
api_name:
 - IOCTL_LAMP_SET_INTENSITY_WHITE
---

# IOCTL_LAMP_SET_INTENSITY_WHITE IOCTL


## -description

The **IOCTL_LAMP_SET_INTENSITY_WHITE** control code sets the lamp to the specified light intensity.

```cpp
#define IOCTL_LAMP_SET_INTENSITY_WHITE \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0005, METHOD_BUFFERED, FILE_ANY_ACCESS)
```

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

`Irp->AssociatedIrp.SystemBuffer` points to a [LAMP_INTENSITY_WHITE](./ns-lamp-lamp_intensity_white.md) structure.

### -input-buffer-length

Length of a [LAMP_INTENSITY_WHITE](./ns-lamp-lamp_intensity_white.md) structure.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The driver sets `Irp->IoStatus.Status` to **STATUS_SUCCESS** or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a  **STATUS_RESOURCE_IN_USE** error via `Irp->IoStatus.Status`.
