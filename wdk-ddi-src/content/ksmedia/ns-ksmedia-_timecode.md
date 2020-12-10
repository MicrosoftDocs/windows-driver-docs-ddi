---
UID: NS:ksmedia._timecode
title: _timecode (ksmedia.h)
description: The TIMECODE union describes a timecode from an external device. This structure is no longer used.
old-location: stream\timecode.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["timecode structure"]
ms.keywords: "*PTIMECODE, PTIMECODE, PTIMECODE union pointer [Streaming Media Devices], TIMECODE, TIMECODE union [Streaming Media Devices], _timecode, ksmedia/PTIMECODE, ksmedia/TIMECODE, stream.timecode, vidcapstruct_80e1d01b-8140-49e8-83bd-210fb38ea0bc.xml"
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
req.typenames: TIMECODE
f1_keywords:
 - _timecode
 - ksmedia/_timecode
 - TIMECODE
 - ksmedia/TIMECODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - TIMECODE
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

<a href="/windows-hardware/drivers/stream/ksproperty-raw-avc-cmd">KSPROPERTY_EXTXPORT_RAW_AVC_CMD</a>
