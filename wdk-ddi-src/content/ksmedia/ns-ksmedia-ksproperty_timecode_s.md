---
UID: NS:ksmedia.__unnamed_struct_136
title: KSPROPERTY_TIMECODE_S (ksmedia.h)
description: The KSPROPERTY_TIMECODE_S structure describes a timecode.
old-location: stream\ksproperty_timecode_s.htm
tech.root: stream
ms.assetid: 45af16ee-7405-44a4-ad14-e2cf9d916164
ms.date: 04/23/2018
ms.keywords: "*PKSPROPERTY_TIMECODE_S, KSPROPERTY_TIMECODE_S, KSPROPERTY_TIMECODE_S structure [Streaming Media Devices], PKSPROPERTY_TIMECODE_S, PKSPROPERTY_TIMECODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TIMECODE_S, ksmedia/PKSPROPERTY_TIMECODE_S, stream.ksproperty_timecode_s, vidcapstruct_03a0e9f7-37b7-4591-8cbc-e1d189c82ef2.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSPROPERTY_TIMECODE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TIMECODE_S, *PKSPROPERTY_TIMECODE_S
---

# KSPROPERTY_TIMECODE_S structure


## -description


The KSPROPERTY_TIMECODE_S structure describes a timecode.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field TimecodeSamp

Specifies the timecode sample. Timecode, absolute track number (ATN) and relative time counter (RTC) are in the <b>TimecodeSamp.timecode.dwFrames</b> member.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565764">KSPROPERTY_TIMECODE_NODE_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568528">TIMECODE_SAMPLE</a>
 

 

