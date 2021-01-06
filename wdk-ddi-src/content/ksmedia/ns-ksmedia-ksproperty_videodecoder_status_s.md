---
UID: NS:ksmedia.__unnamed_struct_112
title: KSPROPERTY_VIDEODECODER_STATUS_S (ksmedia.h)
description: The KSPROPERTY_VIDEODECODER_STATUS_S structure describes the present status of a video decoding device, such as number of lines in the incoming analog signal and whether the signal is locked in.
old-location: stream\ksproperty_videodecoder_status_s.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSPROPERTY_VIDEODECODER_STATUS_S structure"]
ms.keywords: "*PKSPROPERTY_VIDEODECODER_STATUS_S, KSPROPERTY_VIDEODECODER_STATUS_S, KSPROPERTY_VIDEODECODER_STATUS_S structure [Streaming Media Devices], PKSPROPERTY_VIDEODECODER_STATUS_S, PKSPROPERTY_VIDEODECODER_STATUS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEODECODER_STATUS_S, ksmedia/PKSPROPERTY_VIDEODECODER_STATUS_S, stream.ksproperty_videodecoder_status_s, vidcapstruct_c030337a-0c67-4848-84cb-109367a78e07.xml"
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
req.typenames: KSPROPERTY_VIDEODECODER_STATUS_S, *PKSPROPERTY_VIDEODECODER_STATUS_S
f1_keywords:
 - PKSPROPERTY_VIDEODECODER_STATUS_S
 - ksmedia/PKSPROPERTY_VIDEODECODER_STATUS_S
 - KSPROPERTY_VIDEODECODER_STATUS_S
 - ksmedia/KSPROPERTY_VIDEODECODER_STATUS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_VIDEODECODER_STATUS_S
---

# KSPROPERTY_VIDEODECODER_STATUS_S structure


## -description

The KSPROPERTY_VIDEODECODER_STATUS_S structure describes the present status of a video decoding device, such as number of lines in the incoming analog signal and whether the signal is locked in.

## -struct-fields

### -field Property

Specifies an initialized <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field NumberOfLines

Indicates the number of lines detected in the incoming analog video signal.

### -field SignalLocked

Indicates whether the signal is locked. Zero indicates that the signal is not locked. A nonzero value indicates the signal is locked.

## -remarks

The KSPROPERTY_VIDEODECODER_STATUS_S structure retrieves information about the video decoding process, including the number of lines in the incoming analog video signal.

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videodecoder-status">KSPROPERTY_VIDEODECODER_STATUS</a>
