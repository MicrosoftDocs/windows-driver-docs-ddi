---
UID: NF:d4drvif.CTL_CODE
title: CTL_CODE macro (d4drvif.h)
description: "Learn more about: CTL_CODE macro"
ms.date: 10/19/2018
tech.root: print
keywords: ["CTL_CODE macro"]
ms.keywords: CTL_CODE
req.header: d4drvif.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - CTL_CODE
 - d4drvif/CTL_CODE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d4drvif.h
api_name:
 - CTL_CODE
---

# CTL_CODE macro


## -description

The **d4drvif.h** CTL_CODE macro defines IOCTLs for the DOT4 virtual printer port protocol that enables a multi-function printing device to simultaneously send and receive data packets on a single physical channel.

## -parameters

### -param DeviceType

Contains the value for **FILE_DEVICE_DOT4** (0x3a).

### -param Function

Contains the IOCTL Function value (IOCTL_DOT4_USER_BASE base value of 2049 + IOCTL-specific value of 0-9).

### -param Method

Contains the method codes for how buffers are passed for I/O and FS controls:

| Method code | Value |
| --- | --- |
| METHOD_BUFFERED | 0 |
| METHOD_IN_DIRECT | 1 |
| METHOD_OUT_DIRECT | 2 |
| METHOD_NEITHER | 3 |

### -param Access

Contains the access check values:

| Method code | Value |
| --- | --- |
| FILE_ANY_ACCESS | 0x0000 |
| FILE_READ_ACCESS | 0x0001 |
| FILE_WRITE_ACCESS | 0x0002 |

## -remarks

## -see-also

