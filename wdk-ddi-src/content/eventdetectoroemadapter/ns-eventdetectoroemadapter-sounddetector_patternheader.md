---
UID: NS:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0001
title: SOUNDDETECTOR_PATTERNHEADER
author: windows-driver-content
description: The SOUNDDETECTOR_PATTERNHEADER structure specifies the size and the format of the pattern data for the sound detector.
tech.root: audio
ms.assetid: 1aa2d821-a1f6-46ca-be4c-9c8f280f9fa0
ms.author: windowsdriverdev
ms.date: 03/22/2019
keywords: ["SOUNDDETECTOR_PATTERNHEADER structure"]
ms.keywords: SOUNDDETECTOR_PATTERNHEADER, SOUNDDETECTOR_PATTERNHEADER,
req.header: eventdetectoroemadapter.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: SOUNDDETECTOR_PATTERNHEADER
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - __MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0001
 - eventdetectoroemadapter/__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0001
 - SOUNDDETECTOR_PATTERNHEADER
 - eventdetectoroemadapter/SOUNDDETECTOR_PATTERNHEADER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - eventdetectoroemadapter.h
api_name:
 - SOUNDDETECTOR_PATTERNHEADER
product:
 - Windows
---

# SOUNDDETECTOR_PATTERNHEADER structure (eventdetectoroemadapter.h)


## -description

The SOUNDDETECTOR_PATTERNHEADER structure specifies the size and the format of the pattern data for the sound detector.

## -struct-fields

### -field Size

Size of the data including this header.

### -field PatternType

Identifies the format of the pattern data.

## -remarks

This structure is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)