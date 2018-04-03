---
UID: NS:dmusprop._SYNTH_PORTPARAMS
title: "_SYNTH_PORTPARAMS"
author: windows-driver-content
description: The SYNTH_PORTPARAMS structure contains the configuration parameters for a DirectMusic port, which is a DirectMusic term for a device that sends or receives music data.
old-location: audio\synth_portparams.htm
old-project: audio
ms.assetid: 94c953ae-519b-4659-a4c9-a97db7dc31e9
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PSYNTH_PORTPARAMS, PSYNTH_PORTPARAMS, PSYNTH_PORTPARAMS structure pointer [Audio Devices], SYNTH_PORTPARAMS, SYNTH_PORTPARAMS structure [Audio Devices], _SYNTH_PORTPARAMS, aud-prop_33f03864-8052-4dff-9613-1e8046450d16.xml, audio.synth_portparams, dmusprop/PSYNTH_PORTPARAMS, dmusprop/SYNTH_PORTPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dmusprop.h
req.include-header: Dmusprop.h
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
-	dmusprop.h
api_name:
-	SYNTH_PORTPARAMS
product:
- Windows
targetos: Windows
req.typenames: SYNTH_PORTPARAMS, *PSYNTH_PORTPARAMS
---

# _SYNTH_PORTPARAMS structure


## -description


The SYNTH_PORTPARAMS structure contains the configuration parameters for a DirectMusic <i>port</i>, which is a DirectMusic term for a device that sends or receives music data. (In KS terminology, a DirectMusic port does not correspond to a DMus port driver. It corresponds to a render or capture pin on a DirectMusic filter.)


## -struct-fields




### -field ValidParams

Specifies which of the SYNTH_PORTPARAMS structure members contain valid data. This member is a bitfield whose value is either zero or the bitwise OR of one or more of the following flag bits:





#### SYNTH_PORTPARAMS_VOICES

The <b>Voices</b> field is valid.



#### SYNTH_PORTPARAMS_CHANNELGROUPS

The <b>ChannelGroups</b> field is valid.



#### SYNTH_PORTPARAMS_AUDIOCHANNELS

The <b>AudioChannels</b> field is valid.



#### SYNTH_PORTPARAMS_SAMPLERATE

The <b>SampleRate</b> field is valid.



#### SYNTH_PORTPARAMS_EFFECT

The <b>EffectsFlags</b> flag is valid.



#### SYNTH_PORTPARAMS_SHARE

The <b>Share</b> field is valid.


### -field Voices

Specifies the maximum number of simultaneous voices that the application wishes to play on this port.


### -field ChannelGroups

Specifies the number of channel groups requested for this port. Each channel group contains 16 channels.


### -field AudioChannels

Specifies the number of audio channels.


### -field SampleRate

Specifies the number of samples per second for the audio data produced by the port.


### -field EffectsFlags

Specifies the type of effects produced for audio output from this port. This member is a bitfield whose value is either zero or the bitwise OR of one or more of the following flag bits:





#### SYNTH_EFFECT_REVERB

Reverb is enabled.



#### SYNTH_EFFECT_CHORUS

Chorus effect is enabled.



#### SYNTH_EFFECT_DELAY

Delay effect is enabled.

If no effects are enabled, this member is set to SYNTH_EFFECT_NONE, which is zero.


### -field Share

Specifies whether the port's channel groups are shared. When this member is <b>TRUE</b>, all ports use the channel groups assigned to this port. When this member is <b>FALSE</b>, the port is opened in exclusive mode and the use of the same channel groups by other ports is not allowed.


## -remarks



A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537405">KSPROPERTY_SYNTH_PORTPARAMETERS</a> get-property request uses the SYNTH_PORTPARAMS structure for both its property descriptor and its property value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537405">KSPROPERTY_SYNTH_PORTPARAMETERS</a>
 

 

