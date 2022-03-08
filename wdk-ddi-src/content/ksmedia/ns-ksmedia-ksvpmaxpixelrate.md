---
UID: NS:ksmedia.__unnamed_struct_159
title: KSVPMAXPIXELRATE (ksmedia.h)
description: The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port.
tech.root: stream
ms.date: 03/08/2022
keywords: ["KSVPMAXPIXELRATE structure"]
ms.keywords: "*PKSVPMAXPIXELRATE, KSVPMAXPIXELRATE, KSVPMAXPIXELRATE structure [Streaming Media Devices], PKSVPMAXPIXELRATE, PKSVPMAXPIXELRATE structure pointer [Streaming Media Devices], dvdref_c9ca0c83-e189-48b3-a798-95456c07ae0b.xml, ksmedia/KSVPMAXPIXELRATE, ksmedia/PKSVPMAXPIXELRATE, stream.ksvpmaxpixelrate"
f1_keywords:
 - "ksmedia/KSVPMAXPIXELRATE"
 - "KSVPMAXPIXELRATE"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- ksmedia.h
api_name:
- KSVPMAXPIXELRATE
targetos: Windows
req.typenames: KSVPMAXPIXELRATE, *PKSVPMAXPIXELRATE
---

## -description

The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port.

## -struct-fields

### -field Size

Specifies the dimension (width by height) of the video port.

### -field MaxPixelsPerSecond

Indicates the maximum pixel throughput for the selected image size.

### -field Reserved

Reserved for future use.

## -remarks

This structure is used by the [KSPROPERTY_VPCONFIG_MAXPIXELRATE](/windows-hardware/drivers/stream/ksproperty-vpconfig-maxpixelrate) property.

## -see-also

[KSPROPERTY_VPCONFIG_MAXPIXELRATE](/windows-hardware/drivers/stream/ksproperty-vpconfig-maxpixelrate)
