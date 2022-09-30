---
UID: NS:acxpin._ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
tech.root: audio
title: ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
ms.date: 07/22/2022
targetos: Windows
description: The ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION structure specifies how loopback audio is interleaved with the microphone audio for KSPROPERTY_INTERLEAVEDAUDIO_FORMATINFORMATION.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION, *PACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
 - PACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
 - ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
f1_keywords:
 - _ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
 - acxpin/_ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
 - PACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
 - acxpin/PACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
 - ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
 - acxpin/ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION
dev_langs:
 - c++
---

## -description

The **ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION** structure specifies how loopback audio is interleaved with the microphone audio for [KSPROPERTY_INTERLEAVEDAUDIO_FORMATINFORMATION](/windows-hardware/drivers/audio/ksproperty-interleavedaudio-formatinformation).

## -struct-fields

### -field Size

The size of all of the data in the **ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION** structure in bytes.

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

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [KSPROPERTY_INTERLEAVEDAUDIO_FORMATINFORMATION](/windows-hardware/drivers/audio/ksproperty-interleavedaudio-formatinformation)
- [acxpin.h header](index.md)


