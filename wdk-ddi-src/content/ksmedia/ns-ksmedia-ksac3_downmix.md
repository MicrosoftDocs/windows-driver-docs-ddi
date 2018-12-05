---
UID: NS:ksmedia.__unnamed_struct_68
title: KSAC3_DOWNMIX
author: windows-driver-content
description: The KSAC3_DOWNMIX structure specifies whether the program channels in an AC-3-encoded stream need to be downmixed to accommodate the speaker configuration.
old-location: audio\ksac3_downmix.htm
tech.root: audio
ms.assetid: d35450ec-5ddc-4312-bd77-ab7e89690f82
ms.date: 05/08/2018
ms.keywords: "*PKSAC3_DOWNMIX, KSAC3_DOWNMIX, KSAC3_DOWNMIX structure [Audio Devices], PKSAC3_DOWNMIX, PKSAC3_DOWNMIX structure pointer [Audio Devices], aud-prop_24e957af-1fba-467d-93f6-3b7ca211238e.xml, audio.ksac3_downmix, ksmedia/KSAC3_DOWNMIX, ksmedia/PKSAC3_DOWNMIX"
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
-	KSAC3_DOWNMIX
product:
- Windows
targetos: Windows
req.typenames: KSAC3_DOWNMIX, *PKSAC3_DOWNMIX
---

# KSAC3_DOWNMIX structure


## -description


The KSAC3_DOWNMIX structure specifies whether the program channels in an AC-3-encoded stream need to be downmixed to accommodate the speaker configuration.


## -struct-fields




### -field fDownMix

Specifies whether to downmix. If <b>TRUE</b>, downmixing to fewer channels is enabled. The number of output channels depends on the number of speakers present (as specified by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a> property). If <b>FALSE</b>, input and output channels are mapped to speakers on a one-to-one basis. In other words, input channel 0 is mapped to output channel 0, input channel 1 is mapped to output channel 1, and so on, up to the number of encoded channels or speakers, whichever is smaller.


### -field fDolbySurround

Specifies how the output channels are encoded. If <b>TRUE</b>, the output channels are first encoded as two Dolby Surround Pro Logic channels, Lt and Rt. If <b>FALSE</b>, the output channels do not use Dolby Surround Pro Logic encoding.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537218">KSPROPERTY_AC3_DOWNMIX</a> property.

For information about the mapping of output channels to speakers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537218">KSPROPERTY_AC3_DOWNMIX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a>
 

 

