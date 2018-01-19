---
UID: NS:ksmedia.WAVEFORMATEXTENSIBLE
title: WAVEFORMATEXTENSIBLE
author: windows-driver-content
description: The WAVEFORMATEXTENSIBLE structure specifies the format of an audio wave stream.
old-location: audio\waveformatextensible.htm
old-project: audio
ms.assetid: 54bcb18e-df4b-471c-b121-4db75ce5c49b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WAVEFORMATEXTENSIBLE, WAVEFORMATEXTENSIBLE, *PWAVEFORMATEXTENSIBLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Mmreg.h, Ksmedia.h, Mmreg.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WAVEFORMATEXTENSIBLE
req.alt-loc: ksmedia.h
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
req.typenames: WAVEFORMATEXTENSIBLE, *PWAVEFORMATEXTENSIBLE
---

# WAVEFORMATEXTENSIBLE structure



## -description
The WAVEFORMATEXTENSIBLE structure specifies the format of an audio wave stream.



## -syntax

````
typedef struct {
  WAVEFORMATEX Format;
  union {
    WORD wValidBitsPerSample;
    WORD wSamplesPerBlock;
    WORD wReserved;
  } Samples;
  DWORD        dwChannelMask;
  GUID         SubFormat;
} WAVEFORMATEXTENSIBLE, *PWAVEFORMATEXTENSIBLE;
````


## -struct-fields

### -field Format

Specifies the stream's wave-data format. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a>. The <b>wFormat</b> member of WAVEFORMATEX should be set to WAVE_FORMAT_EXTENSIBLE. The <b>wBitsPerSample</b> member of WAVEFORMATEX is defined unambiguously as the size of the container for each sample. Sample containers are always byte-aligned, and <b>wBitsPerSample</b> must be a multiple of eight.


### -field Samples


### -field wValidBitsPerSample

Specifies the precision of the sample in bits. The value of this member should be less than or equal to the container size specified in the <b>Format</b>.<b>wBitsPerSample</b> member. For more information, see the following Remarks section.


### -field wSamplesPerBlock

Specifies the number of samples contained in one compressed block. This value is useful for estimating buffer requirements for compressed formats that have a fixed number of samples within each block. Set this member to zero if each block of compressed audio data contains a variable number of samples. In this case, buffer-estimation and buffer-position information must be obtained in other ways.


### -field wReserved

Reserved for internal use by operating system. Initialize to zero.

</dd>
</dl>

### -field dwChannelMask

Specifies the assignment of channels in the multichannel stream to speaker positions. The encoding is the same as that used for the <b>ActiveSpeakerPositions</b> member of the <a href="..\ksmedia\ns-ksmedia-ksaudio_channel_config.md">KSAUDIO_CHANNEL_CONFIG</a> structure. For more information, see the following Remarks section.


### -field SubFormat

Specifies the subformat. For more information, see the following Remarks section.


## -remarks
WAVEFORMATEXTENSIBLE is an extended form of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a> structure. WAVEFORMATEX can unambiguously describe only a subset of the formats that can be described by WAVEFORMATEXTENSIBLE. WAVEFORMATEXTENSIBLE is not subject to the limitations of WAVEFORMATEX, which is unable to unambiguously specify formats with more than two channels or for which the number of valid bits per sample does not equal the sample container size. For more information, see <a href="https://msdn.microsoft.com/85aa74b4-8e33-49f4-82e7-561baa55c265">Audio Data Formats and Data Ranges</a>.

Frequently, the <b>wValidBitsPerSample</b> member, which specifies the sample precision, contains the same value as the <b>Format</b>.<b>wBitsPerSample</b> member, which specifies the sample container size. However, these values can be different. For example, if the wave data originated from a 20-bit A/D converter, then <b>wValidBitsPerSample</b> should be 20 but <b>Format</b>.<b>wBitsPerSample</b> might be 24 or 32. If <b>wValidBitsPerSample</b> is less than <b>Format</b>.<b>wBitsPerSample</b>, the valid bits (the actual PCM data) are left-aligned within the container. The unused bits in the least-significant portion of the container should be set to zero.

Sample containers begin and end on byte boundaries, and the value of <b>Format</b>.<b>wBitsPerSample</b> should always be a multiple of eight. Also, the value of <b>wValidBitsPerSample</b> should never exceed that of <b>Format</b>.<b>wBitsPerSample</b>. Drivers should reject wave formats that violate these rules.

The WAVEFORMATEXTENSIBLE structure's <b>dwChannelMask</b> member contains a mask indicating which channels are present in the multichannel stream. The least-significant bit represents the front-left speaker, the next bit corresponds to the front-right speaker, and so on. The following flag bits are defined in the header file Ksmedia.h.

SPEAKER_FRONT_LEFT

0x1

SPEAKER_FRONT_RIGHT

0x2

SPEAKER_FRONT_CENTER

0x4

SPEAKER_LOW_FREQUENCY

0x8

SPEAKER_BACK_LEFT

0x10

SPEAKER_BACK_RIGHT

0x20

SPEAKER_FRONT_LEFT_OF_CENTER

0x40

SPEAKER_FRONT_RIGHT_OF_CENTER

0x80

SPEAKER_BACK_CENTER

0x100

SPEAKER_SIDE_LEFT

0x200

SPEAKER_SIDE_RIGHT

0x400

SPEAKER_TOP_CENTER

0x800

SPEAKER_TOP_FRONT_LEFT

0x1000

SPEAKER_TOP_FRONT_CENTER

0x2000

SPEAKER_TOP_FRONT_RIGHT

0x4000

SPEAKER_TOP_BACK_LEFT

0x8000

SPEAKER_TOP_BACK_CENTER

0x10000

SPEAKER_TOP_BACK_RIGHT

0x20000

The channels that are specified in <b>dwChannelMask</b> should be present in the order shown in the preceding table, beginning at the top.

For example, if only front-left and front-center are specified, then front-left and front-center should be in channels 0 and 1, respectively, of the interleaved stream.

As a second example, if <b>nChannels</b> (in the <b>Format</b> member; see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a>) is set to 4 and <b>dwChannelMask</b> is set to 0x00000033, the audio channels are intended for playback to the front-left, front-right, back-left, and back-right speakers. The channel data should be interleaved in that order within each block.

Channel locations beyond the predefined ones are considered reserved.

Alternatively, the channel mask can be specified as one of the following constants, which are defined in Ksmedia.h and are bitwise ORed combinations of the preceding flags that represent standard speaker configurations:

KSAUDIO_SPEAKER_MONO

KSAUDIO_SPEAKER_STEREO

KSAUDIO_SPEAKER_QUAD

KSAUDIO_SPEAKER_SURROUND

KSAUDIO_SPEAKER_5POINT1

KSAUDIO_SPEAKER_7POINT1

KSAUDIO_SPEAKER_DIRECTOUT

A hardware device can be set to one of these speaker configurations by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a>set-property request. For more information about setting speaker configurations, see <a href="..\ksmedia\ns-ksmedia-ksaudio_channel_config.md">KSAUDIO_CHANNEL_CONFIG</a>.

Typically, the count in <b>nChannels</b> equals the number of bits set in <b>dwChannelMask</b>, but this is not necessarily so. If <b>nChannels</b> is less than the number of bits set in <b>dwChannelMask</b>, the extra (most significant) bits in <b>dwChannelMask</b> are ignored. If <b>nChannels</b> exceeds the number of bits set in <b>dwChannelMask</b>, the channels that have no corresponding mask bits are not assigned to any physical speaker position. In any speaker configuration other than KSAUDIO_SPEAKER_DIRECTOUT, an audio sink like KMixer (see <a href="audio.kernel_mode_wdm_audio_components#kmixer_system_driver#kmixer_system_driver">KMixer System Driver</a>) simply ignores these excess channels and mixes only the channels that have corresponding mask bits.

KSAUDIO_SPEAKER_DIRECTOUT represents a configuration with no speakers and is defined in Ksmedia.h as zero. In this configuration, the audio device renders the first channel to the first port on the device, the second channel to the second port on the device, and so on. This allows an audio authoring application to output multichannel data directly and without modification to a device such as a digital mixer or a digital audio storage device (hard disk or ADAT). For example, channels 0 through 30 might contain, respectively, drums, guitar, bass, voice, and so on. For this kind of raw audio data, speaker positions are meaningless, and assigning speaker positions to the input or output streams could cause a component such as KMixer to intervene inappropriately by performing an unwanted format conversion. If a device is unable to process the raw audio streams, it should reject a request to change its speaker configuration to KSAUDIO_SPEAKER_DIRECTOUT. For more information, see <a href="https://msdn.microsoft.com/a4198fb7-157f-40e3-8cca-5a9e392087d2">DSSPEAKER_DIRECTOUT Speaker Configuration</a>.

For more information about multichannel configurations, see the white paper titled <i>Multiple Channel Audio Data and WAVE Files</i> at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8751">audio technology</a> website.

The <b>SubFormat</b> member contains a GUID that specifies the general data format for a wave stream. For example, this GUID might specify that the stream contains integer PCM data. The other members provide additional information such as the sample size and the number of channels. The meaning of the <b>SubFormat</b> GUID is similar to that of the 16-bit format tag in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a> structure's <b>wFormatTag</b> member.

Before WAVEFORMATEXTENSIBLE was introduced in Windows 98 Second Edition, WAVEFORMATEX was the preferred structure for specifying wave formats. At that time, vendors needed to register each new wave format with Microsoft so that an official format tag could be assigned to the format. A list of registered format tags appears in public header file Mmreg.h.

With WAVEFORMATEXTENSIBLE, registering formats is no longer necessary. Vendors can independently assign <b>SubFormat</b> GUIDs to their new formats as needed. However, Microsoft lists some of the more popular <b>SubFormat</b> GUIDs in public header file Ksmedia.h. Before defining a new <b>SubFormat</b> GUID, vendors should check the list of KSDATAFORMAT_SUBTYPE_<i>Xxx</i> constants in Ksmedia.h to see if an appropriate GUID has already been defined for a particular format.

For backward compatibility, any wave format that can be specified by a stand-alone WAVEFORMATEX structure can also be defined by a WAVEFORMATEXTENSIBLE structure. Thus, every format tag in Mmreg.h has a corresponding <b>SubFormat</b> GUID. The following table shows some typical format tags and their corresponding <b>SubFormat</b> GUIDs.

WAVE_FORMAT_PCM

KSDATAFORMAT_SUBTYPE_PCM

WAVE_FORMAT_IEEE_FLOAT

KSDATAFORMAT_SUBTYPE_IEEE_FLOAT

WAVE_FORMAT_DRM

KSDATAFORMAT_SUBTYPE_DRM

WAVE_FORMAT_ALAW

KSDATAFORMAT_SUBTYPE_ALAW

WAVE_FORMAT_MULAW

KSDATAFORMAT_SUBTYPE_MULAW

WAVE_FORMAT_ADPCM

KSDATAFORMAT_SUBTYPE_ADPCM

For more information, see <a href="https://msdn.microsoft.com/299ad5d3-df62-41cf-a18f-daa83cc60ef3">Converting Between Format Tags and Subformat GUIDs</a>.

Because WAVEFORMATEXTENSIBLE is an extended version of WAVEFORMATEX, it can describe additional formats that cannot be described by WAVEFORMATEX alone. Vendors are free to define their own <b>SubFormat</b> GUIDs to identify proprietary formats for which no wave-format tags exist.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-ksaudio_channel_config.md">KSAUDIO_CHANNEL_CONFIG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20WAVEFORMATEXTENSIBLE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

