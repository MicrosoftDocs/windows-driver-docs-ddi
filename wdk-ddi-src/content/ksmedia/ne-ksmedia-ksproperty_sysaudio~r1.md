---
UID: NE:ksmedia.KSPROPERTY_SYSAUDIO~r1
tech.root: audio
title: KSPROPERTY_SYSAUDIO (ksmedia.h)
ms.date: 12/18/2025
targetos: Windows
description: The KSPROPERTY_SYSAUDIO enumeration defines the properties supported by the system audio component (SysAudio).
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ksmedia.h
req.include-header: ksmedia.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: KSPROPERTY_SYSAUDIO
typedef_isUnnamed: false
req.umdf-ver: 
ms.keywords: "KSPROPERTY_SYSAUDIO, KSPROPERTY_SYSAUDIO enumeration [Audio Devices], audio.ksproperty_sysaudio, ksmedia/KSPROPERTY_SYSAUDIO"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_SYSAUDIO
f1_keywords:
 - KSPROPERTY_SYSAUDIO
 - ksmedia/KSPROPERTY_SYSAUDIO
dev_langs:
 - c++
helpviewer_keywords:
 - KSPROPERTY_SYSAUDIO
---

# KSPROPERTY_SYSAUDIO enumeration

## -description

The **KSPROPERTY_SYSAUDIO** enumeration defines the properties supported by the system audio component (SysAudio) for managing virtual audio devices and filter graph construction.

## -enum-fields

### -field KSPROPERTY_SYSAUDIO_DEVICE_COUNT

Retrieves the number of virtual audio devices managed by SysAudio.

### -field KSPROPERTY_SYSAUDIO_DEVICE_FRIENDLY_NAME

Retrieves the friendly name of a specific virtual audio device.

### -field KSPROPERTY_SYSAUDIO_DEVICE_INSTANCE

Retrieves instance information for a virtual audio device.

### -field KSPROPERTY_SYSAUDIO_DEVICE_INTERFACE_NAME

Retrieves the interface name of a virtual audio device.

### -field KSPROPERTY_SYSAUDIO_SELECT_GRAPH

Selects a specific filter graph for audio processing.

### -field KSPROPERTY_SYSAUDIO_CREATE_VIRTUAL_SOURCE

Creates a virtual audio source.

### -field KSPROPERTY_SYSAUDIO_DEVICE_DEFAULT

Specifies or retrieves the default audio device.

### -field KSPROPERTY_SYSAUDIO_ALWAYS_CREATE_VIRTUAL_SOURCE

Reserved for internal Microsoft use.

### -field KSPROPERTY_SYSAUDIO_ADDREMOVE_LOCK

Reserved for internal Microsoft use.

### -field KSPROPERTY_SYSAUDIO_ADDREMOVE_UNLOCK

Reserved for internal Microsoft use.

### -field KSPROPERTY_SYSAUDIO_RENDER_PIN_INSTANCES

Reserved for internal Microsoft use.

### -field KSPROPERTY_SYSAUDIO_RENDER_CONNECTION_INDEX

Reserved for internal Microsoft use.

### -field KSPROPERTY_SYSAUDIO_CREATE_VIRTUAL_SOURCE_ONLY

Reserved for internal Microsoft use.

### -field KSPROPERTY_SYSAUDIO_INSTANCE_INFO

Retrieves detailed instance information.

### -field KSPROPERTY_SYSAUDIO_PREFERRED_DEVICE

Reserved for internal Microsoft use.

### -field KSPROPERTY_SYSAUDIO_COMPONENT_ID

Retrieves the component identifier for a SysAudio device.

### -field KSPROPERTY_SYSAUDIO_ADDREMOVE_GFX

Reserved for internal Microsoft use.

## -remarks

The **KSPROPSETID_SysAudio** property set uses these enumeration values to identify specific properties related to system audio management. SysAudio is a Windows system component that builds and manages filter graphs for audio rendering and capture, presenting them as virtual audio devices to applications.

These properties enable applications to enumerate available audio devices, retrieve device information, select appropriate audio processing graphs, and manage virtual audio sources.

## -see-also

- [KSPROPERTY_SYSAUDIO_PIN](ne-ksmedia-ksproperty_sysaudio_pin-r1.md)
