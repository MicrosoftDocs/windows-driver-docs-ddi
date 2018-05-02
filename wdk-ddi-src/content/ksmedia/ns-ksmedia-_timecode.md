---
UID: NS:ksmedia._timecode
title: "_timecode"
author: windows-driver-content
description: The TIMECODE union describes a timecode from an external device. This structure is no longer used.
old-location: stream\timecode.htm
old-project: stream
ms.assetid: 3387e014-3a62-4d76-ac6d-6446e4fa39d0
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PTIMECODE, PTIMECODE, PTIMECODE union pointer [Streaming Media Devices], TIMECODE, TIMECODE union [Streaming Media Devices], _timecode, ksmedia/PTIMECODE, ksmedia/TIMECODE, stream.timecode, vidcapstruct_80e1d01b-8140-49e8-83bd-210fb38ea0bc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	TIMECODE
product:
- Windows
targetos: Windows
req.typenames: TIMECODE
---

# _timecode structure


## -description


The TIMECODE union describes a timecode from an external device. This structure is no longer used.


## -struct-fields




### -field wFrameRate

Specifies the frame rate.


### -field wFrameFract

Specifies the fractional frame. The full-scale frame is 0x1000.


### -field dwFrames

Specifies a timecode value as a binary frame count.


### -field qw

Specifies the timecode as a quad-word.


## -remarks



This structure is defined for the purpose of searching to a timecode based on an absolute track number (ATN) and/or relative time counter (RTC). However, not all devices support searching to a timecode using this structure.




## -see-also




<a href="https://msdn.microsoft.com/f3ff3815-0f4f-4fcb-89bd-e77d8002813c">KSPROPERTY_EXTXPORT_RAW_AVC_CMD</a>
 

 

