---
UID: NS:ksmedia.KSPROPERTY_TUNER_STANDARD_S
title: KSPROPERTY_TUNER_STANDARD_S (ksmedia.h)
description: The KSPROPERTY_TUNER_STANDARD_S structure describe the standard of a TV tuner device, such as PAL, NTSC or SECAM.
old-location: stream\ksproperty_tuner_standard_s.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSPROPERTY_TUNER_STANDARD_S structure"]
ms.keywords: "*PKSPROPERTY_TUNER_STANDARD_S, KSPROPERTY_TUNER_STANDARD_S, KSPROPERTY_TUNER_STANDARD_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_STANDARD_S, PKSPROPERTY_TUNER_STANDARD_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_STANDARD_S, ksmedia/PKSPROPERTY_TUNER_STANDARD_S, stream.ksproperty_tuner_standard_s, vidcapstruct_b7568a5f-0825-495b-97ff-c8cee17ab8d3.xml"
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
req.typenames: KSPROPERTY_TUNER_STANDARD_S, *PKSPROPERTY_TUNER_STANDARD_S
f1_keywords:
 - PKSPROPERTY_TUNER_STANDARD_S
 - ksmedia/PKSPROPERTY_TUNER_STANDARD_S
 - KSPROPERTY_TUNER_STANDARD_S
 - ksmedia/KSPROPERTY_TUNER_STANDARD_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_TUNER_STANDARD_S
 - KSPROPERTY_TUNER_STANDARD_S
---

# KSPROPERTY_TUNER_STANDARD_S structure


## -description

The KSPROPERTY_TUNER_STANDARD_S structure describe the standard of a TV tuner device, such as PAL, NTSC or SECAM.

## -struct-fields

### -field Property

Specifies an initialized <a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field Standard

Describes an analog video standard. This member may be set to one or more (logically ORed) values from the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a> enumeration.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-tuner-standard">KSPROPERTY_TUNER_STANDARD</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a>



<a href="/windows-hardware/drivers/stream/propsetid-tuner">PROPSETID_TUNER</a>

