---
UID: NS:ksmedia.__unnamed_struct_131
title: KSCAMERA_PERFRAMESETTING_HEADER (ksmedia.h)
description: This structure contains header information for the per-frame settings payload.
old-location: stream\kscamera_perframesetting_header.htm
tech.root: stream
ms.assetid: 2D8A9E54-5551-4DDF-A123-077BA73AE06D
ms.date: 04/30/2019
keywords: ["KSCAMERA_PERFRAMESETTING_HEADER structure"]
ms.keywords: "*PKSCAMERA_PERFRAMESETTING_HEADER, KSCAMERA_PERFRAMESETTING_HEADER, KSCAMERA_PERFRAMESETTING_HEADER structure [Streaming Media Devices], PKSCAMERA_PERFRAMESETTING_HEADER, PKSCAMERA_PERFRAMESETTING_HEADER structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_PERFRAMESETTING_HEADER, ksmedia/PKSCAMERA_PERFRAMESETTING_HEADER, stream.kscamera_perframesetting_header"
f1_keywords:
 - "ksmedia/KSCAMERA_PERFRAMESETTING_HEADER"
 - "KSCAMERA_PERFRAMESETTING_HEADER"
req.header: ksmedia.h
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
- Ksmedia.h
api_name:
- KSCAMERA_PERFRAMESETTING_HEADER
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_PERFRAMESETTING_HEADER, *PKSCAMERA_PERFRAMESETTING_HEADER
---

# KSCAMERA_PERFRAMESETTING_HEADER structure


## -description


This structure contains header information for the per-frame settings payload.


## -struct-fields




### -field Size

The size of this header, frame headers, item headers, value payloads, custom items, and custom data for all frames.


### -field FrameCount

The number of frame settings in this per-frame settings payload.


### -field Id

Not used.


### -field Flags

Not used.


### -field LoopCount

The number of repeats for this per-frame setting. This is always 1.


### -field Reserved

Reserved for future use.

