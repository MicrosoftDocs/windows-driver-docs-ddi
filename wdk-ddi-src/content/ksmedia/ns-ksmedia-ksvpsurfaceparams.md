---
UID: NS:ksmedia.__unnamed_struct_158
title: KSVPSURFACEPARAMS (ksmedia.h)
description: The KSVPSURFACEPARAMS structure is used to describe the surface parameters of a video port surface.
old-location: stream\ksvpsurfaceparams.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSVPSURFACEPARAMS structure"]
ms.keywords: "*PKSVPSURFACEPARAMS, KSVPSURFACEPARAMS, KSVPSURFACEPARAMS structure [Streaming Media Devices], PKSVPSURFACEPARAMS, PKSVPSURFACEPARAMS structure pointer [Streaming Media Devices], dvdref_676b0467-3a23-4aac-8f72-7fd53ef399dd.xml, ksmedia/KSVPSURFACEPARAMS, ksmedia/PKSVPSURFACEPARAMS, stream.ksvpsurfaceparams"
f1_keywords:
 - "ksmedia/KSVPSURFACEPARAMS"
 - "KSVPSURFACEPARAMS"
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
- KSVPSURFACEPARAMS
targetos: Windows
req.typenames: KSVPSURFACEPARAMS, *PKSVPSURFACEPARAMS
---

# KSVPSURFACEPARAMS structure


## -description


The KSVPSURFACEPARAMS structure is used to describe the surface parameters of a video port surface.


## -struct-fields




### -field dwPitch

Specifies the pitch (byte count between subsequent lines) of the video port surface.


### -field dwXOrigin

Indicates the x-origin of the video port surface.


### -field dwYOrigin

Indicates the y-origin of the video port surface.


## -remarks



This structure is used by the <a href="/windows-hardware/drivers/stream/ksproperty-vpconfig-surfaceparams">KSPROPERTY_VPCONFIG_SURFACEPARAMS</a> property.




## -see-also




<a href="/windows-hardware/drivers/stream/ksproperty-vpconfig-surfaceparams">KSPROPERTY_VPCONFIG_SURFACEPARAMS</a>
 

 
