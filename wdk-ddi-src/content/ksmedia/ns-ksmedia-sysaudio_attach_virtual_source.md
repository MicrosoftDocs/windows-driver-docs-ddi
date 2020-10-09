---
UID: NS:ksmedia.__unnamed_struct_61
title: SYSAUDIO_ATTACH_VIRTUAL_SOURCE (ksmedia.h)
description: The SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure is used to attach a mixer-line virtual source (for example, a volume or mute control) to a mixer pin on the virtual audio device.
old-location: audio\sysaudio_attach_virtual_source.htm
tech.root: audio
ms.assetid: 1215cf8e-8e94-4da4-9fb9-2212e8386abd
ms.date: 04/30/2019
keywords: ["SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure"]
ms.keywords: "*PSYSAUDIO_ATTACH_VIRTUAL_SOURCE, PSYSAUDIO_ATTACH_VIRTUAL_SOURCE, PSYSAUDIO_ATTACH_VIRTUAL_SOURCE structure pointer [Audio Devices], SYSAUDIO_ATTACH_VIRTUAL_SOURCE, SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure [Audio Devices], aud-prop_5fce938d-a784-46cf-a65b-3eb0d19db2f8.xml, audio.sysaudio_attach_virtual_source, ksmedia/PSYSAUDIO_ATTACH_VIRTUAL_SOURCE, ksmedia/SYSAUDIO_ATTACH_VIRTUAL_SOURCE"
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
req.typenames: SYSAUDIO_ATTACH_VIRTUAL_SOURCE, *PSYSAUDIO_ATTACH_VIRTUAL_SOURCE
f1_keywords:
 - PSYSAUDIO_ATTACH_VIRTUAL_SOURCE
 - ksmedia/PSYSAUDIO_ATTACH_VIRTUAL_SOURCE
 - SYSAUDIO_ATTACH_VIRTUAL_SOURCE
 - ksmedia/SYSAUDIO_ATTACH_VIRTUAL_SOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - SYSAUDIO_ATTACH_VIRTUAL_SOURCE
---

# SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure


## -description

The SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure is used to attach a mixer-line virtual source (for example, a volume or mute control) to a mixer pin on the virtual audio device.

## -struct-fields

### -field Property

Specifies the property. This parameter is a structure of type <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.

### -field MixerPinId

Specifies the virtual source index.

### -field Reserved

Reserved. Set to zero.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/audio/ksproperty-sysaudio-attach-virtual-source">KSPROPERTY_SYSAUDIO_ATTACH_VIRTUAL_SOURCE</a> property.

## -see-also

<a href="/windows-hardware/drivers/audio/ksproperty-sysaudio-attach-virtual-source">KSPROPERTY_SYSAUDIO_ATTACH_VIRTUAL_SOURCE</a>