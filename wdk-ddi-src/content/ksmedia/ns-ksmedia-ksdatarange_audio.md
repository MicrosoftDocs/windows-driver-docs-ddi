---
UID: NS:ksmedia.__unnamed_struct_20
title: KSDATARANGE_AUDIO (ksmedia.h)
description: The KSDATARANGE_AUDIO structure specifies a range of audio formats.
old-location: audio\ksdatarange_audio.htm
tech.root: audio
ms.assetid: 53631f26-8377-4ab5-83db-ed241c11643a
ms.date: 05/08/2018
keywords: ["KSDATARANGE_AUDIO structure"]
ms.keywords: "*PKSDATARANGE_AUDIO, KSDATARANGE_AUDIO, KSDATARANGE_AUDIO structure [Audio Devices], PKSDATARANGE_AUDIO, PKSDATARANGE_AUDIO structure pointer [Audio Devices], aud-prop_9a59d4cd-4c84-4c22-8a36-741cf53ec08d.xml, audio.ksdatarange_audio, ksmedia/KSDATARANGE_AUDIO, ksmedia/PKSDATARANGE_AUDIO"
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
req.typenames: KSDATARANGE_AUDIO, *PKSDATARANGE_AUDIO
f1_keywords:
 - PKSDATARANGE_AUDIO
 - ksmedia/PKSDATARANGE_AUDIO
 - KSDATARANGE_AUDIO
 - ksmedia/KSDATARANGE_AUDIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSDATARANGE_AUDIO
---

# KSDATARANGE_AUDIO structure


## -description

The KSDATARANGE_AUDIO structure specifies a range of audio formats.

## -struct-fields

### -field DataRange

Specifies the MajorFormat and SubFormat GUIDs as well as the Specifier GUID for the audio data. This member is an initialized <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structure.

### -field MaximumChannels

Specifies the maximum number of channels supported. A value of (ULONG)-1 for this member means that the number of channels has no explicit limit, although the number of channels might be practically limited by the availability of resources such as memory or processing power.

### -field MinimumBitsPerSample

Specifies the minimum bits per sample supported.

### -field MaximumBitsPerSample

Specifies the maximum bits per sample supported.

### -field MinimumSampleFrequency

Specifies the minimum frequency allowed.

### -field MaximumSampleFrequency

Specifies the maximum frequency allowed.

## -remarks

For examples of data ranges that use the KSDATARANGE_AUDIO structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/pcm-stream-data-range">PCM Stream Data Range</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/directsound-stream-data-range">DirectSound Stream Data Range</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/specifying-ac-3-data-ranges">Specifying AC-3 Data Ranges</a>.

For information about data ranges and intersection handling, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/data-intersection-handlers">Data-Intersection Handlers</a>.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>

