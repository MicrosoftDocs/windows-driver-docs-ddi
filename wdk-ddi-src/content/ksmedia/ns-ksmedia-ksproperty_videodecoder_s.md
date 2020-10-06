---
UID: NS:ksmedia.__unnamed_struct_114
title: KSPROPERTY_VIDEODECODER_S (ksmedia.h)
description: The KSPROPERTY_VIDEODECODER_S structure describes property settings in the PROPSETID_VIDCAP_VIDEODECODER property set.
old-location: stream\ksproperty_videodecoder_s.htm
tech.root: stream
ms.assetid: 9444835d-0290-49e7-8f49-a1506ce282cd
ms.date: 04/23/2018
keywords: ["KSPROPERTY_VIDEODECODER_S structure"]
ms.keywords: "*PKSPROPERTY_VIDEODECODER_S, KSPROPERTY_VIDEODECODER_S, KSPROPERTY_VIDEODECODER_S structure [Streaming Media Devices], PKSPROPERTY_VIDEODECODER_S, PKSPROPERTY_VIDEODECODER_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEODECODER_S, ksmedia/PKSPROPERTY_VIDEODECODER_S, stream.ksproperty_videodecoder_s, vidcapstruct_fbca2e77-2e08-4a96-932d-706a7e8b9a2a.xml"
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
req.typenames: KSPROPERTY_VIDEODECODER_S, *PKSPROPERTY_VIDEODECODER_S
f1_keywords:
 - PKSPROPERTY_VIDEODECODER_S
 - ksmedia/PKSPROPERTY_VIDEODECODER_S
 - KSPROPERTY_VIDEODECODER_S
 - ksmedia/KSPROPERTY_VIDEODECODER_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_VIDEODECODER_S
---

# KSPROPERTY_VIDEODECODER_S structure


## -description

The KSPROPERTY_VIDEODECODER_S structure describes property settings in the PROPSETID_VIDCAP_VIDEODECODER property set.

## -struct-fields

### -field Property

Specifies an initialized <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in <b>Property</b> to this value. For Get requests, the minidriver should return the value of the property specified in <b>Property</b>.

## -remarks

The KSPROPERTY_VIDEODECODER_S structure is shared among the KSPROPERTY_VIDEODECODER_STANDARD, KSPROPERTY_VIDEODECODER_OUTPUT_ENABLE, and KSPROPERTY_VIDEODECODER_VCR_TIMING properties within the property set.

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videodecoder-output-enable">KSPROPERTY_VIDEODECODER_OUTPUT_ENABLE</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videodecoder-standard">KSPROPERTY_VIDEODECODER_STANDARD</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videodecoder-vcr-timing">KSPROPERTY_VIDEODECODER_VCR_TIMING</a>