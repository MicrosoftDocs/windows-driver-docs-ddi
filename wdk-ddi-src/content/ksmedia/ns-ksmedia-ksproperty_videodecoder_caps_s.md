---
UID: NS:ksmedia.KSPROPERTY_VIDEODECODER_CAPS_S
title: KSPROPERTY_VIDEODECODER_CAPS_S (ksmedia.h)
description: The KSPROPERTY_VIDEODECODER_CAPS_S structure describes the hardware capabilities of the video decoder device.
old-location: stream\ksproperty_videodecoder_caps_s.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSPROPERTY_VIDEODECODER_CAPS_S structure"]
ms.keywords: "*PKSPROPERTY_VIDEODECODER_CAPS_S, KSPROPERTY_VIDEODECODER_CAPS_S, KSPROPERTY_VIDEODECODER_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_VIDEODECODER_CAPS_S, PKSPROPERTY_VIDEODECODER_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEODECODER_CAPS_S, ksmedia/PKSPROPERTY_VIDEODECODER_CAPS_S, stream.ksproperty_videodecoder_caps_s, vidcapstruct_091e360d-7c9a-4ffc-a7b5-aa634847bbed.xml"
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
req.typenames: KSPROPERTY_VIDEODECODER_CAPS_S, *PKSPROPERTY_VIDEODECODER_CAPS_S
f1_keywords:
 - PKSPROPERTY_VIDEODECODER_CAPS_S
 - ksmedia/PKSPROPERTY_VIDEODECODER_CAPS_S
 - KSPROPERTY_VIDEODECODER_CAPS_S
 - ksmedia/KSPROPERTY_VIDEODECODER_CAPS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_VIDEODECODER_CAPS_S
 - KSPROPERTY_VIDEODECODER_CAPS_S
---

# KSPROPERTY_VIDEODECODER_CAPS_S structure


## -description

The KSPROPERTY_VIDEODECODER_CAPS_S structure describes the hardware capabilities of the video decoder device.

## -struct-fields

### -field Property

Specifies an initialized <a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field StandardsSupported

Specifies the video standards supported by the device. This member may be set to one or more (logically ORed) values from the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a> enumeration.

### -field Capabilities

Specifies video decoder capabilities. This member must be set to zero or one of the values from the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_videodecoder_flags">KS_VIDEODECODER_FLAGS</a> enumeration.

### -field SettlingTime

Specifies the settling time when changing input video sources. This value is expressed in milliseconds.

### -field HSyncPerVSync

Specifies the number of horizontal sync pulses the video decoder produces during the vertical sync period. Decoders that follow the ITU_656 should set this value to six.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videodecoder-caps">KSPROPERTY_VIDEODECODER_CAPS</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_videodecoder_flags">KS_VIDEODECODER_FLAGS</a>



<a href="/windows-hardware/drivers/stream/propsetid-vidcap-videodecoder">PROPSETID_VIDCAP_VIDEODECODER</a>

