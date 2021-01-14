---
UID: NS:ksmedia.__unnamed_struct_8
title: KSAUDIO_PRESENTATION_POSITION (ksmedia.h)
description: The KSAUDIO_PRESENTATION_POSITION structure specifies the current cursor position in audio data stream that is being rendered to the endpoint.
old-location: audio\ksaudio_presentation_position.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["KSAUDIO_PRESENTATION_POSITION structure"]
ms.keywords: "*PKSAUDIO_PRESENTATION_POSITION, KSAUDIO_PRESENTATION_POSITION, KSAUDIO_PRESENTATION_POSITION structure [Audio Devices], PKSAUDIO_PRESENTATION_POSITION, PKSAUDIO_PRESENTATION_POSITION structure pointer [Audio Devices], audio.ksaudio_presentation_position, ksmedia/KSAUDIO_PRESENTATION_POSITION, ksmedia/PKSAUDIO_PRESENTATION_POSITION"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: KSAUDIO_PRESENTATION_POSITION, *PKSAUDIO_PRESENTATION_POSITION
f1_keywords:
 - PKSAUDIO_PRESENTATION_POSITION
 - ksmedia/PKSAUDIO_PRESENTATION_POSITION
 - KSAUDIO_PRESENTATION_POSITION
 - ksmedia/KSAUDIO_PRESENTATION_POSITION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - PKSAUDIO_PRESENTATION_POSITION
 - KSAUDIO_PRESENTATION_POSITION
---

# KSAUDIO_PRESENTATION_POSITION structure


## -description

The <b>KSAUDIO_PRESENTATION_POSITION</b> structure specifies the current cursor position in audio data stream that is being rendered to the endpoint.

## -struct-fields

### -field u64PositionInBlocks

Specifies the block offset from the start of the stream to the current post-decoded, uncompressed position in the stream. A "block" refers to the group of channels in the same sample. So, for example, in a PCM stream a block is the same as a frame. However, for compressed formats a block is a single sample within a frame. This means that for a typical MP3 stream that has 1152 samples in a frame, there are 1152 blocks.

### -field u64QPCPosition

Specifies the value of the performance counter at the time that the audio driver reads the presentation position in response to the <b>KSAUDIO_PRESENTATION_POSITION</b> call. A driver writes to this field with the value read from calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a> when a snapshot is taken of the presentation position.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_presentation_position">KSAUDIO_PRESENTATION_POSITION</a>



<a href="/windows-hardware/drivers/audio/ksproperty-audio-presentation-position">KSPROPERTY_AUDIO_PRESENTATION_POSITION</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>

