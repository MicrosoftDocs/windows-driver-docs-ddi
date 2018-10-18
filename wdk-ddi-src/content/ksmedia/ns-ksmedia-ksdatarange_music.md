---
UID: NS:ksmedia.KSDATARANGE_MUSIC
title: KSDATARANGE_MUSIC
author: windows-driver-content
description: The KSDATARANGE_MUSIC structure specifies a range of DirectMusic MIDI formats.
old-location: audio\ksdatarange_music.htm
tech.root: audio
ms.assetid: 2ada5d1c-9c46-4f7b-99e5-72aa8f6fee9f
ms.date: 5/8/2018
ms.keywords: "*PKSDATARANGE_MUSIC, KSDATARANGE_MUSIC, KSDATARANGE_MUSIC structure [Audio Devices], PKSDATARANGE_MUSIC, PKSDATARANGE_MUSIC structure pointer [Audio Devices], aud-prop_5c82e83d-000e-440e-bfcb-8daef30f5056.xml, audio.ksdatarange_music, ksmedia/KSDATARANGE_MUSIC, ksmedia/PKSDATARANGE_MUSIC"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSDATARANGE_MUSIC
product:
- Windows
targetos: Windows
req.typenames: KSDATARANGE_MUSIC, *PKSDATARANGE_MUSIC
---

# KSDATARANGE_MUSIC structure


## -description


The KSDATARANGE_MUSIC structure specifies a range of DirectMusic MIDI formats.


## -struct-fields




### -field DataRange

Specifies the MajorFormat and SubFormat GUIDs as well as the Specifier GUID for the DirectMusic data. This member is an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a> structure.


### -field Technology

Specifies the type of MIDI output device. This member can be one of the following GUIDs:





#### KSMUSIC_TECHNOLOGY_PORT

The device is a MIDI hardware port.



#### KSMUSIC_TECHNOLOGY_SYNTH

The device is a synthesizer.



#### KSMUSIC_TECHNOLOGY_SQSYNTH

The device is a square-wave synthesizer.



#### KSMUSIC_TECHNOLOGY_FMSYNTH

The device is an FM synthesizer.



#### KSMUSIC_TECHNOLOGY_MAPPER

The device is the Microsoft MIDI mapper.



#### KSMUSIC_TECHNOLOGY_WAVETABLE

The device is a hardware wavetable synthesizer.



#### KSMUSIC_TECHNOLOGY_SWSYNTH

The device is a software synthesizer.


### -field Channels

Specifies the maximum number of simultaneous channels that can be played by an internal synthesizer device. If the device is a port, this member is not meaningful and is set to zero.


### -field Notes

Specifies the maximum number of simultaneous notes that can be played by an internal synthesizer device. If the device is a port, this member is not meaningful and is set to zero.


### -field ChannelMask

Specifies which channels an internal synthesizer device responds to, where the least significant bit refers to channel 0 and the most significant bit to channel 15. Port devices that transmit on all channels set this member to 0xFFFF.


## -remarks



For examples of data ranges that use the KSDATARANGE_MUSIC structure, see <a href="https://msdn.microsoft.com/392eadf7-9c6e-4527-bc84-a2916623c154">MIDI Stream Data Range</a> and <a href="https://msdn.microsoft.com/e3423901-330e-4a86-a921-6678e1c45a97">DirectMusic Stream Data Range</a>.

For information about data ranges and intersection handling, see <a href="https://msdn.microsoft.com/7206afdb-8a34-4b5a-8cea-87119f426161">Data-Intersection Handlers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>
 

 

