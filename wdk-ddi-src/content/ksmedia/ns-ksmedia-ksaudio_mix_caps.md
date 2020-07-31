---
UID: NS:ksmedia.__unnamed_struct_45
title: KSAUDIO_MIX_CAPS (ksmedia.h)
description: The KSAUDIO_MIX_CAPS structure specifies the mixing capabilities of a particular data path from one input channel of a supermixer node (KSNODETYPE_SUPERMIX) to an output channel of the same node.
old-location: audio\ksaudio_mix_caps.htm
tech.root: audio
ms.assetid: d201fdce-ae56-4ba5-a947-e3e0cecc6e17
ms.date: 05/08/2018
keywords: ["KSAUDIO_MIX_CAPS structure"]
ms.keywords: "*PKSAUDIO_MIX_CAPS, KSAUDIO_MIX_CAPS, KSAUDIO_MIX_CAPS structure [Audio Devices], PKSAUDIO_MIX_CAPS, PKSAUDIO_MIX_CAPS structure pointer [Audio Devices], aud-prop_5468df9e-d7f4-4449-a59f-694100f2f825.xml, audio.ksaudio_mix_caps, ksmedia/KSAUDIO_MIX_CAPS, ksmedia/PKSAUDIO_MIX_CAPS"
f1_keywords:
 - "ksmedia/KSAUDIO_MIX_CAPS"
 - "KSAUDIO_MIX_CAPS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSAUDIO_MIX_CAPS
targetos: Windows
req.typenames: KSAUDIO_MIX_CAPS, *PKSAUDIO_MIX_CAPS
---

# KSAUDIO_MIX_CAPS structure


## -description


The KSAUDIO_MIX_CAPS structure specifies the mixing capabilities of a particular data path from one input channel of a supermixer node (<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-supermix">KSNODETYPE_SUPERMIX</a>) to an output channel of the same node. An array of these structures is used by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_mixcap_table">KSAUDIO_MIXCAP_TABLE</a> structure to specify the mixing capabilities for all such paths through a supermixer node.


## -struct-fields




### -field Mute

Specifies whether the data path from the input channel to the output channel is muted (not mixed). A value of <b>TRUE</b> indicates that the data path is muted.


### -field Minimum

Specifies the minimum mix level for the data path from the input channel to the output channel. For more information, see the following Remarks section.


### -field Maximum

Specifies the maximum mix level for the data path from the input channel to the output channel. For more information, see the following Remarks section.


### -field Reset

<b>Reset</b> is a misnomer. This member should have been called Resolution instead. It specifies the resolution of the mix level for the data path from the input channel to the output channel. Resolution values use the following scale: a range from 0 to +2147483647, where 0 is no control and any other number is the number of steps between actual hardware settings in the range between <b>Minimum</b> and <b>Maximum</b>.


### -field Resolution


## -remarks



The mix-level values for the <b>Maximum</b> and <b>Minimum</b> members use the following scale:

-2147483648 is -Infinity decibels (attenuation), 

 -2147483647 is -32767.99998474 decibels (attenuation), and

+2147483647 is +32767.99998474 decibels (gain).

A decibel range represented by integer values -2147483648 to +2147483647, where 

This scale has a resolution of 1/65536 decibel.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_mixcap_table">KSAUDIO_MIXCAP_TABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-supermix">KSNODETYPE_SUPERMIX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-mix-level-caps">KSPROPERTY_AUDIO_MIX_LEVEL_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-mix-level-table">KSPROPERTY_AUDIO_MIX_LEVEL_TABLE</a>
 

 

