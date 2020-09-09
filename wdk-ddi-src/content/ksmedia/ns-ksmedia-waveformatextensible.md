---
UID: NS:ksmedia.__unnamed_struct_2
title: WAVEFORMATEXTENSIBLE (ksmedia.h)
description: The WAVEFORMATEXTENSIBLE structure specifies the format of an audio wave stream.
old-location: audio\waveformatextensible.htm
tech.root: audio
ms.assetid: 54bcb18e-df4b-471c-b121-4db75ce5c49b
ms.date: 08/20/2020
keywords: ["WAVEFORMATEXTENSIBLE structure"]
ms.keywords: "*PWAVEFORMATEXTENSIBLE, PWAVEFORMATEXTENSIBLE, PWAVEFORMATEXTENSIBLE structure pointer [Audio Devices], WAVEFORMATEXTENSIBLE, WAVEFORMATEXTENSIBLE structure [Audio Devices], aud-prop_d40f094e-44f9-4baa-8a15-03e4fb369501.xml, audio.waveformatextensible, ksmedia/PWAVEFORMATEXTENSIBLE, ksmedia/WAVEFORMATEXTENSIBLE"
req.header: ksmedia.h
req.include-header: Mmreg.h, Ksmedia.h, Mmreg.h
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
req.typenames: WAVEFORMATEXTENSIBLE, *PWAVEFORMATEXTENSIBLE
f1_keywords:
 - PWAVEFORMATEXTENSIBLE
 - ksmedia/PWAVEFORMATEXTENSIBLE
 - WAVEFORMATEXTENSIBLE
 - ksmedia/WAVEFORMATEXTENSIBLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - WAVEFORMATEXTENSIBLE
---

# WAVEFORMATEXTENSIBLE structure


## -description

The WAVEFORMATEXTENSIBLE structure specifies the format of an audio wave stream.

## -struct-fields

### -field Format

Specifies the stream's wave-data format. This member is a structure of type [WAVEFORMATEX](https://docs.microsoft.com/windows/win32/api/mmreg/ns-mmreg-waveformatex). The **wFormat** member of WAVEFORMATEX should be set to WAVE_FORMAT_EXTENSIBLE. The **wBitsPerSample** member of WAVEFORMATEX is defined unambiguously as the size of the container for each sample. Sample containers are always byte-aligned, and **wBitsPerSample** must be a multiple of eight.

### -field Samples

### -field Samples.wValidBitsPerSample

Specifies the precision of the sample in bits. The value of this member should be less than or equal to the container size specified in the **Format**.**wBitsPerSample** member. For more information, see the following Remarks section.

### -field Samples.wSamplesPerBlock

Specifies the number of samples contained in one compressed block. This value is useful for estimating buffer requirements for compressed formats that have a fixed number of samples within each block. Set this member to zero if each block of compressed audio data contains a variable number of samples. In this case, buffer-estimation and buffer-position information must be obtained in other ways.

### -field Samples.wReserved

Reserved for internal use by operating system. Initialize to zero.

### -field dwChannelMask

Specifies the assignment of channels in the multichannel stream to speaker positions. The encoding is the same as that used for the **ActiveSpeakerPositions** member of the [KSAUDIO_CHANNEL_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_channel_config) structure. For more information, see the [Remarks](#remarks) section.

### -field SubFormat

Specifies the subformat. For more information, see the [Remarks](#remarks) section.

## -remarks

WAVEFORMATEXTENSIBLE is an extended form of the [WAVEFORMATEX](https://docs.microsoft.com/windows/win32/api/mmreg/ns-mmreg-waveformatex) structure. WAVEFORMATEX can unambiguously describe only a subset of the formats that can be described by WAVEFORMATEXTENSIBLE. WAVEFORMATEXTENSIBLE is not subject to the limitations of WAVEFORMATEX, which is unable to unambiguously specify formats with more than two channels or for which the number of valid bits per sample does not equal the sample container size. For more information, see [Audio Data Formats and Data Ranges](https://docs.microsoft.com/windows-hardware/drivers/audio/audio-data-formats-and-data-ranges).

Frequently, the **wValidBitsPerSample** member, which specifies the sample precision, contains the same value as the **Format**.**wBitsPerSample** member, which specifies the sample container size. However, these values can be different. For example, if the wave data originated from a 20-bit A/D converter, then **wValidBitsPerSample** should be 20 but **Format**.**wBitsPerSample** might be 24 or 32. If **wValidBitsPerSample** is less than **Format**.**wBitsPerSample**, the valid bits (the actual PCM data) are left-aligned within the container. The unused bits in the least-significant portion of the container should be set to zero.

Sample containers begin and end on byte boundaries, and the value of **Format**.**wBitsPerSample** should always be a multiple of eight. Also, the value of **wValidBitsPerSample** should never exceed that of **Format**.**wBitsPerSample**. Drivers should reject wave formats that violate these rules.

The WAVEFORMATEXTENSIBLE structure's **dwChannelMask** member contains a mask indicating which channels are present in the multichannel stream. The least-significant bit represents the front-left speaker, the next bit corresponds to the front-right speaker, and so on. The following flag bits are defined in the header file *Ksmedia.h*.

|Speaker position  |Flag bit  |
|---------|---------|
|SPEAKER_FRONT_LEFT     |      0x1   |
|SPEAKER_FRONT_RIGHT     |   0x2      |
|SPEAKER_FRONT_CENTER     |    0x4     |
|SPEAKER_LOW_FREQUENCY     |    0x8     |
|SPEAKER_BACK_LEFT     | 0x10|
|SPEAKER_BACK_RIGHT     |   0x20      |
|SPEAKER_FRONT_LEFT_OF_CENTER     |   0x40      |
|SPEAKER_FRONT_RIGHT_OF_CENTER     |   0x80      |
|SPEAKER_BACK_CENTER     |     0x100    |
|SPEAKER_SIDE_LEFT     |      0x200   |
|SPEAKER_SIDE_RIGHT     |   0x400      |
|SPEAKER_TOP_CENTER     |      0x800   |
|SPEAKER_TOP_FRONT_LEFT     |   0x1000      |
|SPEAKER_TOP_FRONT_CENTER     |    0x2000     |
|SPEAKER_TOP_FRONT_RIGHT     |     0x4000    |
|SPEAKER_TOP_BACK_LEFT     |     0x8000    |
|SPEAKER_TOP_BACK_CENTER     |     0x10000    |
|SPEAKER_TOP_BACK_RIGHT     |   0x20000      |

The channels that are specified in **dwChannelMask** should be present in the order shown in the preceding table, beginning at the top.

For example, if only front-left and front-center are specified, then front-left and front-center should be in channels 0 and 1, respectively, of the interleaved stream.

As a second example, if **nChannels** (in the **Format** member; see [WAVEFORMATEX](https://docs.microsoft.com/windows/win32/api/mmreg/ns-mmreg-waveformatex)) is set to 4 and **dwChannelMask** is set to 0x00000033, the audio channels are intended for playback to the front-left, front-right, back-left, and back-right speakers. The channel data should be interleaved in that order within each block.

Channel locations beyond the predefined ones are considered reserved.

Alternatively, the channel mask can be specified as one of the following constants, which are defined in *Ksmedia.h* and are bitwise ORed combinations of the preceding flags that represent standard speaker configurations:

KSAUDIO_SPEAKER_MONO

KSAUDIO_SPEAKER_STEREO

KSAUDIO_SPEAKER_QUAD

KSAUDIO_SPEAKER_SURROUND

KSAUDIO_SPEAKER_5POINT1

KSAUDIO_SPEAKER_7POINT1

KSAUDIO_SPEAKER_DIRECTOUT

A hardware device can be set to one of these speaker configurations by a [KSPROPERTY_AUDIO_CHANNEL_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-channel-config) set-property request. For more information about setting speaker configurations, see [KSAUDIO_CHANNEL_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_channel_config).

Typically, the count in **nChannels** equals the number of bits set in **dwChannelMask**, but this is not necessarily so. If **nChannels** is less than the number of bits set in **dwChannelMask**, the extra (most significant) bits in **dwChannelMask** are ignored. If **nChannels** exceeds the number of bits set in **dwChannelMask**, the channels that have no corresponding mask bits are not assigned to any physical speaker position. In any speaker configuration other than KSAUDIO_SPEAKER_DIRECTOUT, an audio sink like KMixer (see [KMixer System Driver](https://docs.microsoft.com/windows-hardware/drivers/audio/kernel-mode-wdm-audio-components)) simply ignores these excess channels and mixes only the channels that have corresponding mask bits.

KSAUDIO_SPEAKER_DIRECTOUT represents a configuration with no speakers and is defined in *Ksmedia.h* as zero. In this configuration, the audio device renders the first channel to the first port on the device, the second channel to the second port on the device, and so on. This allows an audio authoring application to output multichannel data directly and without modification to a device such as a digital mixer or a digital audio storage device (hard disk or ADAT). For example, channels 0 through 30 might contain, respectively, drums, guitar, bass, voice, and so on. For this kind of raw audio data, speaker positions are meaningless, and assigning speaker positions to the input or output streams could cause a component such as KMixer to intervene inappropriately by performing an unwanted format conversion. If a device is unable to process the raw audio streams, it should reject a request to change its speaker configuration to KSAUDIO_SPEAKER_DIRECTOUT. For more information, see [DSSPEAKER_DIRECTOUT Speaker Configuration](https://docs.microsoft.com/windows-hardware/drivers/audio/dsspeaker-directout-speaker-configuration).

For more information about multichannel configurations, see the white paper titled *Multiple Channel Audio Data and WAVE Files* at the [audio technology](https://go.microsoft.com/fwlink/p/?linkid=8751) website.

The **SubFormat** member contains a GUID that specifies the general data format for a wave stream. For example, this GUID might specify that the stream contains integer PCM data. The other members provide additional information such as the sample size and the number of channels. The meaning of the **SubFormat** GUID is similar to that of the 16-bit format tag in the [WAVEFORMATEX](https://docs.microsoft.com/windows/win32/api/mmreg/ns-mmreg-waveformatex) structure's **wFormatTag** member.

Before WAVEFORMATEXTENSIBLE was introduced in Windows 98 Second Edition, WAVEFORMATEX was the preferred structure for specifying wave formats. At that time, vendors needed to register each new wave format with Microsoft so that an official format tag could be assigned to the format. A list of registered format tags appears in public header file *Mmreg.h*.

With WAVEFORMATEXTENSIBLE, registering formats is no longer necessary. Vendors can independently assign **SubFormat** GUIDs to their new formats as needed. However, Microsoft lists some of the more popular **SubFormat** GUIDs in public header file *Ksmedia.h*. Before defining a new **SubFormat** GUID, vendors should check the list of KSDATAFORMAT_SUBTYPE_*Xxx* constants in *Ksmedia.h* to see if an appropriate GUID has already been defined for a particular format.

For backward compatibility, any wave format that can be specified by a stand-alone WAVEFORMATEX structure can also be defined by a WAVEFORMATEXTENSIBLE structure. Thus, every format tag in Mmreg.h has a corresponding **SubFormat** GUID. The following table shows some typical format tags and their corresponding **SubFormat** GUIDs.

| Format tag | SubFormat GUID |
|--|--|
| WAVE_FORMAT_PCM | KSDATAFORMAT_SUBTYPE_PCM |
| WAVE_FORMAT_IEEE_FLOAT | KSDATAFORMAT_SUBTYPE_IEEE_FLOAT |
| WAVE_FORMAT_DRM | KSDATAFORMAT_SUBTYPE_DRM |
| WAVE_FORMAT_ALAW | KSDATAFORMAT_SUBTYPE_ALAW |
| WAVE_FORMAT_MULAW | KSDATAFORMAT_SUBTYPE_MULAW |
| WAVE_FORMAT_ADPCM | KSDATAFORMAT_SUBTYPE_ADPCM |

For more information, see [Converting Between Format Tags and Subformat GUIDs](https://docs.microsoft.com/windows-hardware/drivers/audio/converting-between-format-tags-and-subformat-guids).

Because WAVEFORMATEXTENSIBLE is an extended version of WAVEFORMATEX, it can describe additional formats that cannot be described by WAVEFORMATEX alone. Vendors are free to define their own **SubFormat** GUIDs to identify proprietary formats for which no wave-format tags exist.

## -see-also

[KSAUDIO_CHANNEL_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_channel_config)

[WAVEFORMATEX](https://docs.microsoft.com/windows/win32/api/mmreg/ns-mmreg-waveformatex)

