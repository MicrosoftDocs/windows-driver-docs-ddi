---
UID: NE:ksmedia.KSPROPERTY_SYSAUDIO_PIN~r1
tech.root: audio
title: KSPROPERTY_SYSAUDIO_PIN (ksmedia.h)
ms.date: 09/22/2025
targetos: Windows
description: The KSPROPERTY_SYSAUDIO_PIN enumeration defines the properties supported for SysAudio pin operations.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: KSPROPERTY_SYSAUDIO_PIN
typedef_isUnnamed: false
req.umdf-ver: 
ms.keywords: "KSPROPERTY_SYSAUDIO_PIN, KSPROPERTY_SYSAUDIO_PIN enumeration [Audio Devices], audio.ksproperty_sysaudio_pin, ksmedia/KSPROPERTY_SYSAUDIO_PIN"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_SYSAUDIO_PIN
f1_keywords:
 - KSPROPERTY_SYSAUDIO_PIN
 - ksmedia/KSPROPERTY_SYSAUDIO_PIN
dev_langs:
 - c++
helpviewer_keywords:
 - KSPROPERTY_SYSAUDIO_PIN
---

# KSPROPERTY_SYSAUDIO_PIN enumeration

## -description

The **KSPROPERTY_SYSAUDIO_PIN** enumeration defines the properties supported for SysAudio pin operations and configuration.

## -enum-fields

### -field KSPROPERTY_SYSAUDIO_TOPOLOGY_CONNECTION_INDEX

Retrieves the topology connection index for a SysAudio pin. This property provides information about how pins are connected within the audio topology.

### -field KSPROPERTY_SYSAUDIO_ATTACH_VIRTUAL_SOURCE

Attaches a virtual source to a SysAudio pin. This property enables the connection of virtual audio sources to specific pins for audio processing.

### -field KSPROPERTY_SYSAUDIO_PIN_VOLUME_NODE

Retrieves or sets volume node information for a SysAudio pin. This property allows volume control at the pin level within the SysAudio filter graph.

## -remarks

The **KSPROPSETID_SysAudio_Pin** property set uses these enumeration values to identify specific properties related to SysAudio pin management and control. These properties provide fine-grained control over individual pins within the SysAudio filter graph.

SysAudio pins represent connection points in the audio filter graph where audio data flows between different components. The properties defined in this enumeration allow applications to manage topology connections, attach virtual sources, and control volume settings at the pin level.

## -see-also

- [KSPROPERTY_SYSAUDIO](ne-ksmedia-ksproperty_sysaudio~r1.md)
