---
UID: NS:ksmedia.KSPROPERTY_TIMECODE_S
title: KSPROPERTY_TIMECODE_S (ksmedia.h)
description: The KSPROPERTY_TIMECODE_S structure describes a timecode.
old-location: stream\ksproperty_timecode_s.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSPROPERTY_TIMECODE_S structure"]
ms.keywords: "*PKSPROPERTY_TIMECODE_S, KSPROPERTY_TIMECODE_S, KSPROPERTY_TIMECODE_S structure [Streaming Media Devices], PKSPROPERTY_TIMECODE_S, PKSPROPERTY_TIMECODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TIMECODE_S, ksmedia/PKSPROPERTY_TIMECODE_S, stream.ksproperty_timecode_s, vidcapstruct_03a0e9f7-37b7-4591-8cbc-e1d189c82ef2.xml"
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
req.typenames: KSPROPERTY_TIMECODE_S, *PKSPROPERTY_TIMECODE_S
f1_keywords:
 - PKSPROPERTY_TIMECODE_S
 - ksmedia/PKSPROPERTY_TIMECODE_S
 - KSPROPERTY_TIMECODE_S
 - ksmedia/KSPROPERTY_TIMECODE_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_TIMECODE_S
 - KSPROPERTY_TIMECODE_S
---

# KSPROPERTY_TIMECODE_S structure


## -description

The KSPROPERTY_TIMECODE_S structure describes a timecode.

## -struct-fields

### -field Property

Specifies an initialized <a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field TimecodeSamp

Specifies the timecode sample. Timecode, absolute track number (ATN) and relative time counter (RTC) are in the <b>TimecodeSamp.timecode.dwFrames</b> member.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_timecode_node_s">KSPROPERTY_TIMECODE_NODE_S</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagtimecode_sample">TIMECODE_SAMPLE</a>

