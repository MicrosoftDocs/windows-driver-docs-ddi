---
UID: NS:ksmedia.KSCAMERA_PERFRAMESETTING_FRAME_HEADER
title: KSCAMERA_PERFRAMESETTING_FRAME_HEADER
author: windows-driver-content
description: This structure contains the header information for a frame in a per-frame settings payload.
old-location: stream\kscamera_perframesetting_frame_header.htm
old-project: stream
ms.assetid: 59A52F4B-D987-420D-BF83-1375354C6D6A
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSCAMERA_PERFRAMESETTING_FRAME_HEADER, *PKSCAMERA_PERFRAMESETTING_FRAME_HEADER, KSCAMERA_PERFRAMESETTING_FRAME_HEADER
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
req.alt-api: KSCAMERA_PERFRAMESETTING_FRAME_HEADER
req.alt-loc: Ksmedia.h
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
req.typenames: *PKSCAMERA_PERFRAMESETTING_FRAME_HEADER, KSCAMERA_PERFRAMESETTING_FRAME_HEADER
---

# KSCAMERA_PERFRAMESETTING_FRAME_HEADER structure



## -description
This structure contains the header information for a frame in a per-frame settings payload.



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Id;
  ULONG ItemCount;
  ULONG Reserved;
} KSCAMERA_PERFRAMESETTING_FRAME_HEADER, *PKSCAMERA_PERFRAMESETTING_FRAME_HEADER;
````


## -struct-fields

### -field Size

The size of this header, all the item headers, value payloads, custom items, and custom data for this frame.


### -field Id

The frame ID in the range of 0 and KSCAMERA_PERFRAMESETTING_HEADER.FrameCount - 1.


### -field ItemCount

The number of item settings for this frame. The value 0 indicates using global settings for this frame.


### -field Reserved

Reserved for future use.


## -remarks
