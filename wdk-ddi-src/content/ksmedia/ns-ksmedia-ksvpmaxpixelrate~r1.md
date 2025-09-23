---
UID: NS:ksmedia.KSVPMAXPIXELRATE~r1
tech.root: display
title: KSVPMAXPIXELRATE (ksmedia.h)
ms.date: 09/22/2025
targetos: Windows
description: The KSVPMAXPIXELRATE structure describes the maximum pixel processing rate for a video port.
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
req.typenames: KSVPMAXPIXELRATE, *PKSVPMAXPIXELRATE
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ms.keywords: "*PKSVPMAXPIXELRATE, KSVPMAXPIXELRATE, KSVPMAXPIXELRATE structure [Display Devices], PKSVPMAXPIXELRATE, PKSVPMAXPIXELRATE structure pointer [Display Devices], display.ksvpmaxpixelrate, ksmedia/KSVPMAXPIXELRATE, ksmedia/PKSVPMAXPIXELRATE"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSVPMAXPIXELRATE
 - PKSVPMAXPIXELRATE
f1_keywords:
 - KSVPMAXPIXELRATE
 - ksmedia/KSVPMAXPIXELRATE
 - PKSVPMAXPIXELRATE
 - ksmedia/PKSVPMAXPIXELRATE
dev_langs:
 - c++
helpviewer_keywords:
 - KSVPMAXPIXELRATE
---

# KSVPMAXPIXELRATE structure

## -description

The **KSVPMAXPIXELRATE** structure describes the maximum pixel processing rate for a video port in pixels per second.

## -struct-fields

### -field Size

Specifies the size of the structure in bytes. This field is used to ensure proper structure versioning and validation.

### -field MaxPixelsPerSecond

Specifies the maximum number of pixels that the video port can process per second. This value determines the bandwidth limitations of the video port and affects the supported video formats and resolutions.

### -field Reserved

Reserved for system use. This field should be set to zero and should not be modified by applications.

## -remarks

This structure is used with video port-related properties to specify or query the maximum pixel processing capabilities of a video port. The maximum pixel rate is an important factor in determining what video formats and resolutions can be supported by a particular video port configuration.

Video port drivers use this information to validate requested video formats and to optimize performance by selecting appropriate processing parameters within the hardware's capabilities.

## -see-also

- [KSVPSIZE_PROP](ns-ksmedia-ksvpsize_prop~r1.md)
- [KSVPSURFACEPARAMS](ns-ksmedia-ksvpsurfaceparams~r1.md)
