---
UID: NS:ksmedia.KSVPSIZE_PROP~r1
tech.root: display
title: KSVPSIZE_PROP (ksmedia.h)
ms.date: 09/22/2025
targetos: Windows
description: The KSVPSIZE_PROP structure describes the size properties for a video port operation.
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
req.typenames: KSVPSIZE_PROP, *PKSVPSIZE_PROP
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ms.keywords: "*PKSVPSIZE_PROP, KSVPSIZE_PROP, KSVPSIZE_PROP structure [Display Devices], PKSVPSIZE_PROP, PKSVPSIZE_PROP structure pointer [Display Devices], display.ksvpsize_prop, ksmedia/KSVPSIZE_PROP, ksmedia/PKSVPSIZE_PROP"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSVPSIZE_PROP
 - PKSVPSIZE_PROP
f1_keywords:
 - KSVPSIZE_PROP
 - ksmedia/KSVPSIZE_PROP
 - PKSVPSIZE_PROP
 - ksmedia/PKSVPSIZE_PROP
dev_langs:
 - c++
helpviewer_keywords:
 - KSVPSIZE_PROP
---

# KSVPSIZE_PROP structure

## -description

The **KSVPSIZE_PROP** structure describes the size properties for a video port operation.

## -struct-fields

### -field Property

Specifies a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that identifies the property set, property ID, and request type for the video port size property.

### -field Size

Specifies the size dimensions for the video port operation. This field defines the width and height of the video data to be processed by the video port.

## -remarks

This structure is used with video port properties to specify or query size-related parameters for video port operations. The size information is essential for configuring the video port to handle specific video formats and resolutions.

Video port drivers use this information to set up the appropriate hardware configuration for processing video data of the specified dimensions.

## -see-also

- [KSVPMAXPIXELRATE](ns-ksmedia-ksvpmaxpixelrate~r1.md)
- [KSVPSURFACEPARAMS](ns-ksmedia-ksvpsurfaceparams~r1.md)
- [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)
