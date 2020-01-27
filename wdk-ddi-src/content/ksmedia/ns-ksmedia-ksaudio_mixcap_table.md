---
UID: NS:ksmedia.__unnamed_struct_46
title: KSAUDIO_MIXCAP_TABLE (ksmedia.h)
description: The KSAUDIO_MIXCAP_TABLE structure specifies the mixing capabilities of a supermixer node (KSNODETYPE_SUPERMIX). This structure is used to get or set the data value for the KSPROPERTY_AUDIO_MIX_LEVEL_CAPS property.
old-location: audio\ksaudio_mixcap_table.htm
tech.root: audio
ms.assetid: 508d73f6-1660-4663-87f5-8dbd1dff153a
ms.date: 05/08/2018
ms.keywords: "*PKSAUDIO_MIXCAP_TABLE, KSAUDIO_MIXCAP_TABLE, KSAUDIO_MIXCAP_TABLE structure [Audio Devices], PKSAUDIO_MIXCAP_TABLE, PKSAUDIO_MIXCAP_TABLE structure pointer [Audio Devices], aud-prop_42fdfffa-fb37-4a29-8015-065cec552815.xml, audio.ksaudio_mixcap_table, ksmedia/KSAUDIO_MIXCAP_TABLE, ksmedia/PKSAUDIO_MIXCAP_TABLE"
f1_keywords:
 - "ksmedia/KSAUDIO_MIXCAP_TABLE"
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
- KSAUDIO_MIXCAP_TABLE
product:
- Windows
targetos: Windows
req.typenames: KSAUDIO_MIXCAP_TABLE, *PKSAUDIO_MIXCAP_TABLE
---

# KSAUDIO_MIXCAP_TABLE structure

## -description

The KSAUDIO_MIXCAP_TABLE structure specifies the mixing capabilities of a supermixer node ([KSNODETYPE_SUPERMIX](https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-supermix)). This structure is used to get or set the data value for the [KSPROPERTY_AUDIO_MIX_LEVEL_CAPS](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-mix-level-caps) property.

## -struct-fields

### -field InputChannels

Specifies the number of input channels.

### -field OutputChannels

Specifies the number of output channels.

### -field Capabilities

Contains the first entry in a two-dimensional array of [KSAUDIO_MIX_CAPS](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_mix_caps) structures. Given a supermixer node with *m* input channels and *n* output channels, the array contains *m** elements. Each element describes the mix-level capabilities of the path from a particular input channel to a particular output channel.

## -remarks

The **Capabilities** table is stored as a two-dimensional array:

```cpp
KSAUDIO_MIX_CAPS Capabilities[M*N];
```

The table is an M-by-N matrix that maps M input channels into N output channels. The following table shows the mapping of **Capabilities** array elements to the supermixer node's M*N input-output paths.

| Array element | Input-output path |
| --- | --- |
| Capabilities[0] | Input channel 0 to output channel 0 |
| Capabilities[1] | Input channel 0 to output channel 1 |
| Capabilities[N-1] | Input channel 0 to output channel N-1 |
| Capabilities[N] | Input channel 1 to output channel 0 |
| Capabilities[N+1] | Input channel 1 to output channel 1 |
| Capabilities[2N-1] | Input channel 1 to output channel N-1 |
| Capabilities[M*N-1] | Input channel M-1 to output channel N-1 |

In other words, the mixer caps for the path from input channel *i* to output channel *j* are contained in **Capabilities**[*i* * N + *j*]. If no path exists from input *i* to output *j*, set the **Mute** member of matrix element (*i*,*j*) to **TRUE**.

The size of the table is calculated from the KSAUDIO_MIXCAP_TABLE structure that is retrieved by a [KSPROPERTY_AUDIO_MIX_LEVEL_CAPS](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-mix-level-caps) get property request. If the structure's **InputChannels** and **OutputChannels** members have the values *m* and *n*, the total storage required for the KSAUDIO_MIXCAP_TABLE structure plus the KSAUDIO_MIX_CAPS array is calculated as

**sizeof**(KSAUDIO_MIXCAP_TABLE) + (*mn - 1*)**sizeof**(KSAUDIO_MIX_CAPS)

If the client sends an initial KSPROPERTY_AUDIO_MIX_LEVEL_CAPS request in which the property size is specified as 2***sizeof**(ULONG), the miniport driver should fill in only the first two members of the KSAUDIO_MIXCAP_TABLE structure, **InputChannels** and **OutputChannels**. The client can then send a second property request with enough storage allocated to contain the capabilities of all the channels.

## -see-also

[KSAUDIO_MIX_CAPS](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_mix_caps)

[KSNODETYPE_SUPERMIX](https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-supermix)

[KSPROPERTY_AUDIO_MIX_LEVEL_CAPS](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-mix-level-caps)

[KSPROPERTY_AUDIO_MIX_LEVEL_TABLE](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-mix-level-table)
