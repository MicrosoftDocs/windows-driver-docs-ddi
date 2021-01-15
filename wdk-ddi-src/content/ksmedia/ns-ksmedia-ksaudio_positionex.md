---
UID: NS:ksmedia.__unnamed_struct_48
title: KSAUDIO_POSITIONEX (ksmedia.h)
description: The KSAUDIO_POSITIONEX structure specifies the stream position and the associated timestamp information for a kernel streaming (KS)-based audio driver.
old-location: audio\ksaudio_positionex.htm
tech.root: audio
ms.date: 04/30/2019
keywords: ["KSAUDIO_POSITIONEX structure"]
ms.keywords: "*PKSAUDIO_POSITIONEX, KSAUDIO_POSITIONEX, KSAUDIO_POSITIONEX structure [Audio Devices], PKSAUDIO_POSITIONEX, PKSAUDIO_POSITIONEX structure pointer [Audio Devices], aud-prop_9a418d76-9a4f-4626-b6db-64ed4fcedb18.xml, audio.ksaudio_positionex, ksmedia/KSAUDIO_POSITIONEX, ksmedia/PKSAUDIO_POSITIONEX"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.typenames: KSAUDIO_POSITIONEX, *PKSAUDIO_POSITIONEX
f1_keywords:
 - PKSAUDIO_POSITIONEX
 - ksmedia/PKSAUDIO_POSITIONEX
 - KSAUDIO_POSITIONEX
 - ksmedia/KSAUDIO_POSITIONEX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSAUDIO_POSITIONEX
 - KSAUDIO_POSITIONEX
---

# KSAUDIO_POSITIONEX structure


## -description

The KSAUDIO_POSITIONEX structure specifies the stream position and the associated timestamp information for a kernel streaming (KS)-based audio driver.

## -struct-fields

### -field TimerFrequency

Specifies the number of ticks per second for the timer that produces the timestamps.

### -field TimeStamp1

Specifies the timestamp that is taken immediately prior to the acquisition of the position information.

### -field Position

Specifies the position of the read cursor and the write cursor in the audio buffer of an audio stream.

### -field TimeStamp2

Specifies the timestamp that is taken immediately after the acquisition of the position information.

## -remarks

A KS-based audio driver can use the KSAUDIO_POSITIONEX structure along with the <a href="/windows-hardware/drivers/audio/ksproperty-audio-positionex">KSPROPERTY_AUDIO_POSITIONEX</a> property to return a stream position and a timestamp.

## -see-also

<a href="/windows-hardware/drivers/audio/ksproperty-audio-positionex">KSPROPERTY_AUDIO_POSITIONEX</a>

