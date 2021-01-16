---
UID: NS:ksmedia.__unnamed_struct_43
title: KSAUDIO_DYNAMIC_RANGE (ksmedia.h)
description: The KSAUDIO_DYNAMIC_RANGE structure specifies the dynamic range of an audio stream. This structure is used to get or set the data value for the KSPROPERTY_AUDIO_DYNAMIC_RANGE property.
old-location: audio\ksaudio_dynamic_range.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["KSAUDIO_DYNAMIC_RANGE structure"]
ms.keywords: "*PKSAUDIO_DYNAMIC_RANGE, KSAUDIO_DYNAMIC_RANGE, KSAUDIO_DYNAMIC_RANGE structure [Audio Devices], PKSAUDIO_DYNAMIC_RANGE, PKSAUDIO_DYNAMIC_RANGE structure pointer [Audio Devices], aud-prop_1b73d842-9ef4-4017-b30a-26373b4797b4.xml, audio.ksaudio_dynamic_range, ksmedia/KSAUDIO_DYNAMIC_RANGE, ksmedia/PKSAUDIO_DYNAMIC_RANGE"
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
req.typenames: KSAUDIO_DYNAMIC_RANGE, *PKSAUDIO_DYNAMIC_RANGE
f1_keywords:
 - PKSAUDIO_DYNAMIC_RANGE
 - ksmedia/PKSAUDIO_DYNAMIC_RANGE
 - KSAUDIO_DYNAMIC_RANGE
 - ksmedia/KSAUDIO_DYNAMIC_RANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSAUDIO_DYNAMIC_RANGE
 - KSAUDIO_DYNAMIC_RANGE
---

# KSAUDIO_DYNAMIC_RANGE structure


## -description

The KSAUDIO_DYNAMIC_RANGE structure specifies the dynamic range of an audio stream. This structure is used to get or set the data value for the <a href="/windows-hardware/drivers/audio/ksproperty-audio-dynamic-range">KSPROPERTY_AUDIO_DYNAMIC_RANGE</a> property.

## -struct-fields

### -field QuietCompression

Specifies the compression level for soft sounds. This value ranges from 0 to 100 percent (represented as 0xFFFFFFFF) of the linear range compression for soft sounds. The higher this value, the higher the volume of soft sounds.

### -field LoudCompression

Specifies the compression level for loud sounds. This value ranges from 0 to 100 percent (represented as 0xFFFFFFFF) of the linear range compression for loud sounds. The higher this value, the lower the volume of loud sounds.

## -remarks

By default, both structure members are set to zero percent, which reproduces the full dynamic range of the audio stream.

## -see-also

<a href="/windows-hardware/drivers/audio/ksproperty-audio-dynamic-range">KSPROPERTY_AUDIO_DYNAMIC_RANGE</a>

