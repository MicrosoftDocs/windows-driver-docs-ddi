---
UID: NS:dmusprop._SYNTHVOICEPRIORITY_INSTANCE
title: _SYNTHVOICEPRIORITY_INSTANCE (dmusprop.h)
description: The SYNTHVOICEPRIORITY_INSTANCE structure identifies a voice in a MIDI synthesizer by specifying the voice's channel group (set of 16 MIDI channels) and its channel number within that group.
old-location: audio\synthvoicepriority_instance.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["SYNTHVOICEPRIORITY_INSTANCE structure"]
ms.keywords: "*PSYNTHVOICEPRIORITY_INSTANCE, PSYNTHVOICEPRIORITY_INSTANCE, PSYNTHVOICEPRIORITY_INSTANCE structure pointer [Audio Devices], SYNTHVOICEPRIORITY_INSTANCE, SYNTHVOICEPRIORITY_INSTANCE structure [Audio Devices], _SYNTHVOICEPRIORITY_INSTANCE, aud-prop_86a44512-a1b5-4380-a96a-5e9184ff71c2.xml, audio.synthvoicepriority_instance, dmusprop/PSYNTHVOICEPRIORITY_INSTANCE, dmusprop/SYNTHVOICEPRIORITY_INSTANCE"
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
targetos: Windows
req.typenames: SYNTHVOICEPRIORITY_INSTANCE, *PSYNTHVOICEPRIORITY_INSTANCE
f1_keywords:
 - _SYNTHVOICEPRIORITY_INSTANCE
 - dmusprop/_SYNTHVOICEPRIORITY_INSTANCE
 - PSYNTHVOICEPRIORITY_INSTANCE
 - dmusprop/PSYNTHVOICEPRIORITY_INSTANCE
 - SYNTHVOICEPRIORITY_INSTANCE
 - dmusprop/SYNTHVOICEPRIORITY_INSTANCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dmusprop.h
api_name:
 - SYNTHVOICEPRIORITY_INSTANCE
---

# _SYNTHVOICEPRIORITY_INSTANCE structure


## -description

The SYNTHVOICEPRIORITY_INSTANCE structure identifies a voice in a MIDI synthesizer by specifying the voice's channel group (set of 16 MIDI channels) and its channel number within that group.

## -struct-fields

### -field ChannelGroup

Specifies the channel group that the voice belongs to. Channel groups are numbered beginning at zero. Each channel group contains 16 channels.

### -field Channel

Specifies the channel that the voice is on. This member contains a channel number in the range 0 through 15. It identifies a channel in the channel group.

## -remarks

The <a href="/previous-versions/ff537407(v=vs.85)">KSPROPERTY_SYNTH_VOICEPRIORITY</a> property request uses the SYNTHVOICEPRIORITY_INSTANCE structure for its property descriptor. The structure specifies which voice gets priority when the miniport driver needs to bump voices from the cache.

## -see-also

<a href="/previous-versions/ff537407(v=vs.85)">KSPROPERTY_SYNTH_VOICEPRIORITY</a>
