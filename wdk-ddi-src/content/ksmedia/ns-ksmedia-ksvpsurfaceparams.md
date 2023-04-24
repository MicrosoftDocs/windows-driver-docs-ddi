---
UID: NS:ksmedia.KSVPSURFACEPARAMS
title: KSVPSURFACEPARAMS (ksmedia.h)
description: The KSVPSURFACEPARAMS structure is used to describe the surface parameters of a video port surface.
tech.root: stream
ms.date: 03/08/2022
keywords: ["KSVPSURFACEPARAMS structure"]
ms.keywords: "*PKSVPSURFACEPARAMS, KSVPSURFACEPARAMS, KSVPSURFACEPARAMS structure [Streaming Media Devices], PKSVPSURFACEPARAMS, PKSVPSURFACEPARAMS structure pointer [Streaming Media Devices], dvdref_676b0467-3a23-4aac-8f72-7fd53ef399dd.xml, ksmedia/KSVPSURFACEPARAMS, ksmedia/PKSVPSURFACEPARAMS, stream.ksvpsurfaceparams"
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
targetos: Windows
req.typenames: KSVPSURFACEPARAMS, *PKSVPSURFACEPARAMS
f1_keywords:
 - "ksmedia/KSVPSURFACEPARAMS"
 - "KSVPSURFACEPARAMS"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSVPSURFACEPARAMS
---

## -description

The **KSVPSURFACEPARAMS** structure is used to describe the surface parameters of a video port surface.

## -struct-fields

### -field dwPitch

Specifies the pitch (byte count between subsequent lines) of the video port surface.

### -field dwXOrigin

Indicates the X-origin of the video port surface.

### -field dwYOrigin

Indicates the Y-origin of the video port surface.

## -remarks

This structure is used by the [KSPROPERTY_VPCONFIG_SURFACEPARAMS](/windows-hardware/drivers/stream/ksproperty-vpconfig-surfaceparams) property.

## -see-also

[KSPROPERTY_VPCONFIG_SURFACEPARAMS](/windows-hardware/drivers/stream/ksproperty-vpconfig-surfaceparams)

