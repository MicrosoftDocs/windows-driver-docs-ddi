---
UID: NS:ntddvdeo.VIDEO_CLUT
tech.root: display
title: VIDEO_CLUT
ms.date: 11/01/2024
targetos: Windows
description: Learn more about the VIDEO_CLUT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddvdeo.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: VIDEO_CLUT, *PVIDEO_CLUT
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - VIDEO_CLUT
 - PVIDEO_CLUT
f1_keywords:
 - VIDEO_CLUT
 - ntddvdeo/VIDEO_CLUT
 - PVIDEO_CLUT
 - ntddvdeo/PVIDEO_CLUT
dev_langs:
 - c++
helpviewer_keywords:
 - VIDEO_CLUT
---

## -description

The **VIDEO_CLUT** structure is used to define a color look-up table (CLUT) for a video device.

## -struct-fields

### -field NumEntries

Number of entries in the **LookupTable** array.

### -field FirstEntry

Location in the device palette to which the first entry in the **LookupTable** of colors should be copied to. The other entries in the **LookupTable** should be copied sequentially, from this starting point into the device's palette.

### -field RgbArray

VIDEO_CLUTDATA structure with RGB values.

### -field RgbLong

Generic 32-bit value that can be used to access the color entries in the **LookupTable**.

### -field LookupTable[1]

Union with array of color entries to copy into the device's color registers/palette. The color entries can be accessed as a generic 32-bit value or as Red/Green/Blue/Unused fields.
