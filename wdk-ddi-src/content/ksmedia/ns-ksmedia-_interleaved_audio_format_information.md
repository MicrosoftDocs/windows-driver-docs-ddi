---
UID: NS:ksmedia.__unnamed_struct_38
title: INTERLEAVED_AUDIO_FORMAT_INFORMATION
description: The INTERLEAVED_AUDIO_FORMAT_INFORMATION structure specifies how loopback audio is interleaved with the microphone audio for KSPROPERTY_INTERLEAVEDAUDIO_FORMATINFORMATION.
tech.root: audio
ms.date: 08/14/2020
keywords: ["INTERLEAVED_AUDIO_FORMAT_INFORMATION structure"]
ms.keywords: INTERLEAVED_AUDIO_FORMAT_INFORMATION, INTERLEAVED_AUDIO_FORMAT_INFORMATION,
req.header: ksmedia.h
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
req.typenames: INTERLEAVED_AUDIO_FORMAT_INFORMATION
targetos: Windows
f1_keywords:
 - INTERLEAVED_AUDIO_FORMAT_INFORMATION
 - ksmedia/INTERLEAVED_AUDIO_FORMAT_INFORMATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - INTERLEAVED_AUDIO_FORMAT_INFORMATION
---

# INTERLEAVED_AUDIO_FORMAT_INFORMATION structure


## -description

The **INTERLEAVED_AUDIO_FORMAT_INFORMATION** structure specifies how loopback audio is interleaved with the microphone audio for [KSPROPERTY_INTERLEAVEDAUDIO_FORMATINFORMATION](/windows-hardware/drivers/audio/ksproperty-interleavedaudio-formatinformation).

## -struct-fields

### -field Size

The size of all of the data in the  INTERLEAVED_AUDIO_FORMAT_INFORMATION structure in bytes.

### -field PrimaryChannelCount

The number of the primary channels. This is typically the number of microphone elements when interleaving the microphone and loopback audio.

### -field PrimaryChannelStartPosition

The array index of the first channel for the primary audio.

### -field PrimaryChannelMask

The primary channel mask, KSAUDIO_SPEAKER_MONO, KSAUDIO_SPEAKER_STEREO, etc.

### -field InterleavedChannelCount

The number of interleaved channels. This is typically the number of channels for the loopback audio associated with the primary channels.

### -field InterleavedChannelStartPosition

The array index of the first channel for the interleaved audio.

### -field InterleavedChannelMask

The interleaved channel mask, KSAUDIO_SPEAKER_MONO, KSAUDIO_SPEAKER_STEREO, etc.

## -remarks

The data described by this structure is intended only for the Hardware Keyword Spotter pin and provides a way to include loopback audio interleaved with the microphone audio. This is done by interleaving the Hardware Keyword Spotter pin audio and loopback audio together into a single PCM audio stream and then communicating, via this property, the channels containing loopback vs. microphone audio.

The WAVEFORMATEXTENSIBLE returned by the driver reports the channel count as a sum of the primary and loopback audio, with a channel mask appropriate for the total channel count. The primary and interleaved audio must have matching bits per sample, sample rate, etc. This structure communicates all information needed to split the two streams of data.

## -see-also

[KSPROPERTY_INTERLEAVEDAUDIO_FORMATINFORMATION](/windows-hardware/drivers/audio/ksproperty-interleavedaudio-formatinformation)

[KSPROPERTY_INTERLEAVEDAUDIO Enumeration](./ne-ksmedia-ksproperty_interleavedaudio.md)
