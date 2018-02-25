---
UID: NS:ksmedia.KSCAMERA_PERFRAMESETTING_HEADER
title: KSCAMERA_PERFRAMESETTING_HEADER
author: windows-driver-content
description: This structure contains header information for the per-frame settings payload.
old-location: stream\kscamera_perframesetting_header.htm
old-project: stream
ms.assetid: 2D8A9E54-5551-4DDF-A123-077BA73AE06D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSCAMERA_PERFRAMESETTING_HEADER, ,, A, C, D, E, F, G, H, I, K, KSCAMERA_PERFRAMESETTING_HEADER, KSCAMERA_PERFRAMESETTING_HEADER structure [Streaming Media Devices], M, N, P, PKSCAMERA_PERFRAMESETTING_HEADER, PKSCAMERA_PERFRAMESETTING_HEADER structure pointer [Streaming Media Devices], R, S, T, _, ksmedia/KSCAMERA_PERFRAMESETTING_HEADER, ksmedia/PKSCAMERA_PERFRAMESETTING_HEADER, stream.kscamera_perframesetting_header"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSCAMERA_PERFRAMESETTING_HEADER
product: Windows
targetos: Windows
req.typenames: KSCAMERA_PERFRAMESETTING_HEADER, *PKSCAMERA_PERFRAMESETTING_HEADER
---

# KSCAMERA_PERFRAMESETTING_HEADER structure


## -description


This structure contains header information for the per-frame settings payload.


## -syntax


````
typedef struct {
  ULONG     Size;
  ULONG     FrameCount;
  GUID      Id;
  ULONGLONG Flags;
  ULONG     LoopCount;
  ULONG     Reserved;
} KSCAMERA_PERFRAMESETTING_HEADER, *PKSCAMERA_PERFRAMESETTING_HEADER;
````


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

