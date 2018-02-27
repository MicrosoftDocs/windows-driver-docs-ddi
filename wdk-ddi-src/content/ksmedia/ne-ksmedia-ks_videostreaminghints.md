---
UID: NE:ksmedia.KS_VideoStreamingHints
title: KS_VideoStreamingHints
author: windows-driver-content
description: The KS_VideoStreamingHints enumeration defines video compression hints.
old-location: stream\ks_videostreaminghints.htm
old-project: stream
ms.assetid: 06f26404-c955-4034-8dd3-ad641c7b8010
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KS_StreamingHint_CompQuality, KS_StreamingHint_CompWindowSize, KS_StreamingHint_FrameInterval, KS_StreamingHint_KeyFrameRate, KS_StreamingHint_PFrameRate, KS_VideoStreamingHints, KS_VideoStreamingHints enumeration [Streaming Media Devices], ksmedia/KS_StreamingHint_CompQuality, ksmedia/KS_StreamingHint_CompWindowSize, ksmedia/KS_StreamingHint_FrameInterval, ksmedia/KS_StreamingHint_KeyFrameRate, ksmedia/KS_StreamingHint_PFrameRate, ksmedia/KS_VideoStreamingHints, stream.ks_videostreaminghints, vidcapstruct_d26d7d11-bfb8-4773-8ace-05793a7a7084.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KS_VideoStreamingHints
product: Windows
targetos: Windows
req.typenames: KS_VideoStreamingHints
---

# KS_VideoStreamingHints enumeration


## -description


The KS_VideoStreamingHints enumeration defines video compression hints.


## -syntax


````
typedef enum  { 
  KS_StreamingHint_FrameInterval   = 0x0100,
  KS_StreamingHint_KeyFrameRate    = 0x0200,
  KS_StreamingHint_PFrameRate      = 0x0400,
  KS_StreamingHint_CompQuality     = 0x0800,
  KS_StreamingHint_CompWindowSize  = 0x1000
} KS_VideoStreamingHints;
````


## -enum-fields




### -field KS_StreamingHint_FrameInterval

Specifies compression that is based on the interval between video frames.


### -field KS_StreamingHint_KeyFrameRate

Specifies compression that is based on key frames.


### -field KS_StreamingHint_PFrameRate

Specifies compression that is based on predicted frames.


### -field KS_StreamingHint_CompQuality

Specifies compression that is based on compression quality.


### -field KS_StreamingHint_CompWindowSize

Specifies compression that is based on compression window size.

