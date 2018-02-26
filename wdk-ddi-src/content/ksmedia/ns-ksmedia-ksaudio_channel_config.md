---
UID: NS:ksmedia.KSAUDIO_CHANNEL_CONFIG
title: KSAUDIO_CHANNEL_CONFIG
author: windows-driver-content
description: The KSAUDIO_CHANNEL_CONFIG structure specifies the configuration of channels within the data format of an audio stream.
old-location: audio\ksaudio_channel_config.htm
old-project: audio
ms.assetid: 64e46fd5-f6bf-425d-b2a5-c938f8e565b9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSAUDIO_CHANNEL_CONFIG, ,, A, C, D, E, F, G, H, I, K, KSAUDIO_CHANNEL_CONFIG, KSAUDIO_CHANNEL_CONFIG structure [Audio Devices], L, N, O, P, PKSAUDIO_CHANNEL_CONFIG, PKSAUDIO_CHANNEL_CONFIG structure pointer [Audio Devices], S, U, _, aud-prop_e81a721c-474b-4b51-8bed-df294a477050.xml, audio.ksaudio_channel_config, ksmedia/KSAUDIO_CHANNEL_CONFIG, ksmedia/PKSAUDIO_CHANNEL_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSAUDIO_CHANNEL_CONFIG
product: Windows
targetos: Windows
req.typenames: KSAUDIO_CHANNEL_CONFIG, *PKSAUDIO_CHANNEL_CONFIG
---

# KSAUDIO_CHANNEL_CONFIG structure


## -description


The KSAUDIO_CHANNEL_CONFIG structure specifies the configuration of channels within the data format of an audio stream.


## -syntax


````
typedef struct {
  LONG ActiveSpeakerPositions;
} KSAUDIO_CHANNEL_CONFIG, *PKSAUDIO_CHANNEL_CONFIG;
````


## -struct-fields




### -field ActiveSpeakerPositions

Specifies both the number of channels and the assignment of those channels to speaker positions. This member is a bitmask in which each bit within the mask corresponds to a particular speaker position. If a mask bit is set, the audio stream contains a channel that is assigned to the speaker position that the mask bit represents. The number of channels in the stream is obtained by counting how many number ones appear in the bitmask. For more information, see the following Remarks section.


## -remarks



This structure is used to set or get the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a> property.

The following table shows the flag bits that are defined for the <b>ActiveSpeakerPositions</b> member.

<table>
<tr>
<th>Speaker position</th>
<th>Flag bit</th>
</tr>
<tr>
<td>
SPEAKER_FRONT_LEFT

</td>
<td>
0x1

</td>
</tr>
<tr>
<td>
SPEAKER_FRONT_RIGHT

</td>
<td>
0x2

</td>
</tr>
<tr>
<td>
SPEAKER_FRONT_CENTER

</td>
<td>
0x4

</td>
</tr>
<tr>
<td>
SPEAKER_LOW_FREQUENCY

</td>
<td>
0x8

</td>
</tr>
<tr>
<td>
SPEAKER_BACK_LEFT

</td>
<td>
0x10

</td>
</tr>
<tr>
<td>
SPEAKER_BACK_RIGHT

</td>
<td>
0x20

</td>
</tr>
<tr>
<td>
SPEAKER_FRONT_LEFT_OF_CENTER

</td>
<td>
0x40

</td>
</tr>
<tr>
<td>
SPEAKER_FRONT_RIGHT_OF_CENTER

</td>
<td>
0x80

</td>
</tr>
<tr>
<td>
SPEAKER_BACK_CENTER

</td>
<td>
0x100

</td>
</tr>
<tr>
<td>
SPEAKER_SIDE_LEFT

</td>
<td>
0x200

</td>
</tr>
<tr>
<td>
SPEAKER_SIDE_RIGHT

</td>
<td>
0x400

</td>
</tr>
<tr>
<td>
SPEAKER_TOP_CENTER

</td>
<td>
0x800

</td>
</tr>
<tr>
<td>
SPEAKER_TOP_FRONT_LEFT

</td>
<td>
0x1000

</td>
</tr>
<tr>
<td>
SPEAKER_TOP_FRONT_CENTER

</td>
<td>
0x2000

</td>
</tr>
<tr>
<td>
SPEAKER_TOP_FRONT_RIGHT

</td>
<td>
0x4000

</td>
</tr>
<tr>
<td>
SPEAKER_TOP_BACK_LEFT

</td>
<td>
0x8000

</td>
</tr>
<tr>
<td>
SPEAKER_TOP_BACK_CENTER

</td>
<td>
0x10000

</td>
</tr>
<tr>
<td>
SPEAKER_TOP_BACK_RIGHT

</td>
<td>
0x20000

</td>
</tr>
</table>
 

Each audio data format contains channels for one or more of the preceding speaker positions. The number of channels simply equals the number of nonzero flag bits in the <b>ActiveSpeakerPositions</b> member.

The relative positions of the channels within each block of audio data always follow the same relative ordering as the flag bits in the preceding table. For example, if <b>ActiveSpeakerPositions</b> contains the value 0x00000033, the format defines four audio channels that are assigned for playback to the front-left, front-right, back-left, and back-right speakers, respectively. The channel data should be interleaved in that order within each block. (This is the KSAUDIO_SPEAKER_QUAD configuration that appears in the second of the two following tables.)

The following table shows the speaker configurations that are defined for DVD.

<table>
<tr>
<th>Configuration</th>
<th>Speaker position</th>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_GROUND_FRONT_LEFT

</td>
<td>
SPEAKER_FRONT_LEFT

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_GROUND_FRONT_CENTER

</td>
<td>
SPEAKER_FRONT_CENTER

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_GROUND_FRONT_RIGHT

</td>
<td>
SPEAKER_FRONT_RIGHT

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_GROUND_REAR_LEFT

</td>
<td>
SPEAKER_BACK_LEFT

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_GROUND_REAR_RIGHT

</td>
<td>
SPEAKER_BACK_RIGHT

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_TOP_MIDDLE

</td>
<td>
SPEAKER_TOP_CENTER

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_SUPER_WOOFER

</td>
<td>
SPEAKER_LOW_FREQUENCY

</td>
</tr>
</table>
 

The following table shows the speaker configurations that are defined for DirectSound.

<table>
<tr>
<th>Configuration</th>
<th>Speaker positions</th>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_DIRECTOUT

</td>
<td>
0 (no speakers)

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_MONO

</td>
<td>
(SPEAKER_FRONT_CENTER)

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_STEREO

</td>
<td>
(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT)

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_QUAD

</td>
<td>
(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT | SPEAKER_BACK_LEFT | SPEAKER_BACK_RIGHT)

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_SURROUND

</td>
<td>
(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT | SPEAKER_FRONT_CENTER | SPEAKER_BACK_CENTER)

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_5POINT1

</td>
<td>
(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT | SPEAKER_FRONT_CENTER | SPEAKER_LOW_FREQUENCY | SPEAKER_BACK_LEFT | SPEAKER_BACK_RIGHT)

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_5POINT1_SURROUND

</td>
<td>
(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT |

SPEAKER_FRONT_CENTER | SPEAKER_LOW_FREQUENCY |

SPEAKER_SIDE_LEFT  | SPEAKER_SIDE_RIGHT)

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_7POINT1

</td>
<td>
(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT | SPEAKER_FRONT_CENTER | SPEAKER_LOW_FREQUENCY | SPEAKER_BACK_LEFT | SPEAKER_BACK_RIGHT | SPEAKER_FRONT_LEFT_OF_CENTER | SPEAKER_FRONT_RIGHT_OF_CENTER)

</td>
</tr>
<tr>
<td>
KSAUDIO_SPEAKER_7POINT1_SURROUND

</td>
<td>
(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT |

SPEAKER_FRONT_CENTER | SPEAKER_LOW_FREQUENCY |

SPEAKER_BACK_LEFT | SPEAKER_BACK_RIGHT |

SPEAKER_SIDE_LEFT | SPEAKER_SIDE_RIGHT)

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  The KSAUDIO_SPEAKER_7POINT1 speaker configuration,  is obsolete and no longer supported in Windows Vista and later versions of Windows.</div>
<div> </div>
In the preceding table, the constant KSAUDIO_SPEAKER_DIRECTOUT has a value of zero, which means that no speaker positions are assigned to the channels in the multichannel stream. For example, channel zero might represent percussion, channel 1 might represent trumpet, channel 2 might represent voice, and so on. In this configuration, the channels in the input stream are output directly to the hardware without modification and without being interpreted as speaker positions. For more information, see <a href="https://msdn.microsoft.com/a4198fb7-157f-40e3-8cca-5a9e392087d2">DSSPEAKER_DIRECTOUT Speaker Configuration</a>.

The speaker configuration for a 5.1-channel surround format is defined by the constant KSAUDIO_SPEAKER_5POINT1_SURROUND in the preceding table. The geometric layout of the speakers is shown in the following figure, which shows the positions of the front-left, front-right, front-center, side-left, and side-right speakers. The figure omits the low-frequency speaker because it is nondirectional.

<img alt="Diagram illustrating a 5.1-channel surround speaker configuration; the low-frequency speaker is not shown" src="images/spkrposn_new.png"/>
For this example, the following list shows the ordering of the six channels within each block of audio data:

<ol>
<li>
SPEAKER_FRONT_LEFT

</li>
<li>
SPEAKER_FRONT_RIGHT

</li>
<li>
SPEAKER_FRONT_CENTER

</li>
<li>
SPEAKER_LOW_FREQUENCY

</li>
<li>
SPEAKER_SIDE_LEFT

</li>
<li>
SPEAKER_SIDE_RIGHT

</li>
</ol>
For a PCM format with a 16-bit sample size, each block of audio data occupies 12 bytes, which are ordered as shown in the following table.

<table>
<tr>
<th>Byte</th>
<th>Audio data</th>
</tr>
<tr>
<td>
0

</td>
<td>
Front Left (8 LSBs)

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Front Left (8 MSBs)

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Front Right (8 LSBs)

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Front Right (8 MSBs)

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Front Center (8 LSBs)

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Front Center (8 MSBs)

</td>
</tr>
<tr>
<td>
6

</td>
<td>
Low Freq (8 LSBs)

</td>
</tr>
<tr>
<td>
7

</td>
<td>
Low Freq (8 MSBs)

</td>
</tr>
<tr>
<td>
8

</td>
<td>
Side Left (8 LSBs)

</td>
</tr>
<tr>
<td>
9

</td>
<td>
Side Left (8 MSBs)

</td>
</tr>
<tr>
<td>
10

</td>
<td>
Side Right (8 LSBs)

</td>
</tr>
<tr>
<td>
11

</td>
<td>
Side Right (8 MSBs)

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a>



<a href="..\ksmedia\ns-ksmedia-waveformatextensible.md">WAVEFORMATEXTENSIBLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_CHANNEL_CONFIG structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

