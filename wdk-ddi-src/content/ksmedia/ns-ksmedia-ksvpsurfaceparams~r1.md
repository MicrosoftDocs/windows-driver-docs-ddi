---
UID: NS:ksmedia.KSVPSURFACEPARAMS~r1
tech.root: display
title: KSVPSURFACEPARAMS (ksmedia.h)
ms.date: 12/18/2025
targetos: Windows
description: The KSVPSURFACEPARAMS structure describes the surface parameters for a video port operation.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: KSVPSURFACEPARAMS, *PKSVPSURFACEPARAMS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ms.keywords: "*PKSVPSURFACEPARAMS, KSVPSURFACEPARAMS, KSVPSURFACEPARAMS structure [Display Devices], PKSVPSURFACEPARAMS, PKSVPSURFACEPARAMS structure pointer [Display Devices], display.ksvpsurfaceparams, ksmedia/KSVPSURFACEPARAMS, ksmedia/PKSVPSURFACEPARAMS"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSVPSURFACEPARAMS
 - PKSVPSURFACEPARAMS
f1_keywords:
 - KSVPSURFACEPARAMS
 - ksmedia/KSVPSURFACEPARAMS
 - PKSVPSURFACEPARAMS
 - ksmedia/PKSVPSURFACEPARAMS
dev_langs:
 - c++
helpviewer_keywords:
 - KSVPSURFACEPARAMS
---

# KSVPSURFACEPARAMS structure

## -description

The **KSVPSURFACEPARAMS** structure describes the surface parameters for a video port operation, including pitch, origin coordinates, and surface dimensions.

## -struct-fields

### -field dwPitch

Specifies the pitch (width in bytes) of the video surface. This value indicates the number of bytes between the start of one scan line and the start of the next scan line in the surface buffer.

### -field dwXOrigin

Specifies the horizontal origin (X coordinate) of the video data within the surface. This value determines the starting pixel position for horizontal placement of the video data.

### -field dwYOrigin

Specifies the vertical origin (Y coordinate) of the video data within the surface. This value determines the starting pixel position for vertical placement of the video data.

## -remarks

This structure is used with video port properties to specify the surface parameters for video port operations. These parameters define how video data is organized and positioned within a surface buffer, which is essential for proper video rendering and display.

The pitch value is particularly important for video processing as it accounts for any alignment requirements or additional padding that may exist between scan lines in the surface buffer. The origin coordinates allow for flexible positioning of video data within a larger surface area.

## -see-also

- [KSVPMAXPIXELRATE](ns-ksmedia-ksvpmaxpixelrate-r1.md)
- [KSVPSIZE_PROP](ns-ksmedia-ksvpsize_prop-r1.md)
