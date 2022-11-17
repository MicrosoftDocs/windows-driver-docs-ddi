---
UID: NS:ksmedia.__unnamed_struct_42
title: KSAUDIO_CHANNEL_CONFIG (ksmedia.h)
description: The KSAUDIO_CHANNEL_CONFIG structure specifies the configuration of channels within the data format of an audio stream.
tech.root: audio
ms.date: 11/17/2022
keywords: ["KSAUDIO_CHANNEL_CONFIG structure"]
ms.keywords: "*PKSAUDIO_CHANNEL_CONFIG, KSAUDIO_CHANNEL_CONFIG, KSAUDIO_CHANNEL_CONFIG structure [Audio Devices], PKSAUDIO_CHANNEL_CONFIG, PKSAUDIO_CHANNEL_CONFIG structure pointer [Audio Devices], aud-prop_e81a721c-474b-4b51-8bed-df294a477050.xml, audio.ksaudio_channel_config, ksmedia/KSAUDIO_CHANNEL_CONFIG, ksmedia/PKSAUDIO_CHANNEL_CONFIG"
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
req.typenames: KSAUDIO_CHANNEL_CONFIG, *PKSAUDIO_CHANNEL_CONFIG
f1_keywords:
 - PKSAUDIO_CHANNEL_CONFIG
 - ksmedia/PKSAUDIO_CHANNEL_CONFIG
 - KSAUDIO_CHANNEL_CONFIG
 - ksmedia/KSAUDIO_CHANNEL_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSAUDIO_CHANNEL_CONFIG
 - KSAUDIO_CHANNEL_CONFIG
---

## -description

The **KSAUDIO_CHANNEL_CONFIG** structure specifies the configuration of channels within the data format of an audio stream.

## -struct-fields

### -field ActiveSpeakerPositions

Specifies both the number of channels and the assignment of those channels to speaker positions. This member is a bitmask in which each bit within the mask corresponds to a particular speaker position. If a mask bit is set, the audio stream contains a channel that is assigned to the speaker position that the mask bit represents. The number of channels in the stream is obtained by counting how many number ones appear in the bitmask. For more information, see the following Remarks section.

## -remarks

This structure is used to set or get the data value for the [KSPROPERTY_AUDIO_CHANNEL_CONFIG](/windows-hardware/drivers/audio/ksproperty-audio-channel-config) property.

The following table shows the flag bits that are defined for the **ActiveSpeakerPositions** member.

| Speaker position | Flag bit |
|---|---|
| SPEAKER_FRONT_LEFT | 0x1 |
| SPEAKER_FRONT_RIGHT | 0x2 |
| SPEAKER_FRONT_CENTER | 0x4 |
| SPEAKER_LOW_FREQUENCY | 0x8 |
| SPEAKER_BACK_LEFT | 0x10 |
| SPEAKER_BACK_RIGHT | 0x20 |
| SPEAKER_FRONT_LEFT_OF_CENTER | 0x40 |
| SPEAKER_FRONT_RIGHT_OF_CENTER | 0x80 |
| SPEAKER_BACK_CENTER | 0x100 |
| SPEAKER_SIDE_LEFT | 0x200 |
| SPEAKER_SIDE_RIGHT | 0x400 |
| SPEAKER_TOP_CENTER | 0x800 |
| SPEAKER_TOP_FRONT_LEFT | 0x1000 |
| SPEAKER_TOP_FRONT_CENTER | 0x2000 |
| SPEAKER_TOP_FRONT_RIGHT | 0x4000 |
| SPEAKER_TOP_BACK_LEFT | 0x8000 |
| SPEAKER_TOP_BACK_CENTER | 0x10000 |
| SPEAKER_TOP_BACK_RIGHT | 0x20000 |

Each audio data format contains channels for one or more of the preceding speaker positions. The number of channels simply equals the number of nonzero flag bits in the **ActiveSpeakerPositions** member.

The relative positions of the channels within each block of audio data always follow the same relative ordering as the flag bits in the preceding table. For example, if **ActiveSpeakerPositions** contains the value 0x00000033, the format defines four audio channels that are assigned for playback to the front-left, front-right, back-left, and back-right speakers, respectively. The channel data should be interleaved in that order within each block. (This is the KSAUDIO_SPEAKER_QUAD configuration that appears in the second of the two following tables.)

The following table shows the speaker configurations that are defined for DVD.

| Configuration | Speaker position |
|---|---|
| KSAUDIO_SPEAKER_GROUND_FRONT_LEFT | SPEAKER_FRONT_LEFT |
| KSAUDIO_SPEAKER_GROUND_FRONT_CENTER | SPEAKER_FRONT_CENTER |
| KSAUDIO_SPEAKER_GROUND_FRONT_RIGHT | SPEAKER_FRONT_RIGHT |
| KSAUDIO_SPEAKER_GROUND_REAR_LEFT | SPEAKER_BACK_LEFT |
| KSAUDIO_SPEAKER_GROUND_REAR_RIGHT | SPEAKER_BACK_RIGHT |
| KSAUDIO_SPEAKER_TOP_MIDDLE | SPEAKER_TOP_CENTER |
| KSAUDIO_SPEAKER_SUPER_WOOFER | SPEAKER_LOW_FREQUENCY |

The following table shows the speaker configurations that are defined for DirectSound.

| Configuration | Speaker positions |
|---|---|
| KSAUDIO_SPEAKER_DIRECTOUT | 0 (no speakers) |
| KSAUDIO_SPEAKER_MONO | SPEAKER_FRONT_CENTER |
| KSAUDIO_SPEAKER_STEREO | SPEAKER_FRONT_LEFT |
|  | SPEAKER_FRONT_RIGHT |
| KSAUDIO_SPEAKER_QUAD | SPEAKER_FRONT_LEFT |
|  | SPEAKER_FRONT_RIGHT |
|  | SPEAKER_BACK_LEFT |
|  | SPEAKER_BACK_RIGHT |
| KSAUDIO_SPEAKER_SURROUND | SPEAKER_FRONT_LEFT |
|  | SPEAKER_FRONT_RIGHT |
|  | SPEAKER_FRONT_CENTER |
|  | SPEAKER_BACK_CENTER |
| KSAUDIO_SPEAKER_5POINT1 | SPEAKER_FRONT_LEFT |
|  | SPEAKER_FRONT_RIGHT |
|  | SPEAKER_FRONT_CENTER |
|  | SPEAKER_LOW_FREQUENCY |
|  | SPEAKER_BACK_LEFT |
|  | SPEAKER_BACK_RIGHT |
| KSAUDIO_SPEAKER_5POINT1_SURROUND | SPEAKER_FRONT_LEFT |
|  | SPEAKER_FRONT_RIGHT |
|  | SPEAKER_LOW_FREQUENCY |
|  | SPEAKER_SIDE_LEFT |
|  | SPEAKER_SIDE_RIGHT |
| KSAUDIO_SPEAKER_7POINT1 | SPEAKER_FRONT_LEFT |
|  | SPEAKER_FRONT_RIGHT |
|  | SPEAKER_FRONT_CENTER |
|  | SPEAKER_LOW_FREQUENCY |
|  | SPEAKER_BACK_LEFT |
|  | SPEAKER_BACK_RIGHT |
|  | SPEAKER_FRONT_LEFT_OF_CENTER |
|  | SPEAKER_FRONT_RIGHT_OF_CENTER |
| KSAUDIO_SPEAKER_7POINT1_SURROUND | SPEAKER_FRONT_LEFT |
|  | SPEAKER_FRONT_RIGHT |
|  | SPEAKER_FRONT_CENTER |
|  | SPEAKER_LOW_FREQUENCY |
|  | SPEAKER_BACK_LEFT |
|  | SPEAKER_BACK_RIGHT |
|  | SPEAKER_SIDE_LEFT |
|  | SPEAKER_SIDE_RIGHT |

> [!NOTE]
> The KSAUDIO_SPEAKER_7POINT1 speaker configuration, is obsolete and no longer supported in Windows Vista and later versions of Windows.

In the preceding table, the constant KSAUDIO_SPEAKER_DIRECTOUT has a value of zero, which means that no speaker positions are assigned to the channels in the multichannel stream. For example, channel zero might represent percussion, channel 1 might represent trumpet, channel 2 might represent voice, and so on. In this configuration, the channels in the input stream are output directly to the hardware without modification and without being interpreted as speaker positions. For more information, see [DSSPEAKER_DIRECTOUT Speaker Configuration](/windows-hardware/drivers/audio/dsspeaker-directout-speaker-configuration).

The speaker configuration for a 5.1-channel surround format is defined by the constant KSAUDIO_SPEAKER_5POINT1_SURROUND in the preceding table. The geometric layout of the speakers is shown in the following figure, which shows the positions of the front-left, front-right, front-center, side-left, and side-right speakers. The figure omits the low-frequency speaker because it is nondirectional.

![Diagram illustrating a 5.1-channel surround speaker configuration; the low-frequency speaker is not shown.](../images/audio-spkrposn-new.png)

For this example, the following list shows the ordering of the six channels within each block of audio data:

1. SPEAKER_FRONT_LEFT

1. SPEAKER_FRONT_RIGHT

1. SPEAKER_FRONT_CENTER

1. SPEAKER_LOW_FREQUENCY

1. SPEAKER_SIDE_LEFT

1. SPEAKER_SIDE_RIGHT

For a PCM format with a 16-bit sample size, each block of audio data occupies 12 bytes, which are ordered as shown in the following table.

| Byte | Audio data |
|---|---|
| 0 | Front Left (8 LSBs) |
| 1 | Front Left (8 MSBs) |
| 2 | Front Right (8 LSBs) |
| 3 | Front Right (8 MSBs) |
| 4 | Front Center (8 LSBs) |
| 5 | Front Center (8 MSBs) |
| 6 | Low Freq (8 LSBs) |
| 7 | Low Freq (8 MSBs) |
| 8 | Side Left (8 LSBs) |
| 9 | Side Left (8 MSBs) |
| 10 | Side Right (8 LSBs) |
| 11 | Side Right (8 MSBs) |

## -see-also

[KSPROPERTY_AUDIO_CHANNEL_CONFIG](/windows-hardware/drivers/audio/ksproperty-audio-channel-config)

[WAVEFORMATEXTENSIBLE](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-waveformatextensible)
