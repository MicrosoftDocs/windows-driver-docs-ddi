---
UID: NS:audiosensors._AUDIO_MODULE_ID
tech.root: audio
title: AUDIO_MODULE_ID
ms.date: 09/26/2025
targetos: Windows
description: The AUDIO_MODULE_ID structure identifies a specific audio module within an audio device.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: audiosensors.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: AUDIO_MODULE_ID, *PAUDIO_MODULE_ID
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - audiosensors.h
api_name:
 - _AUDIO_MODULE_ID
 - PAUDIO_MODULE_ID
 - AUDIO_MODULE_ID
f1_keywords:
 - _AUDIO_MODULE_ID
 - audiosensors/_AUDIO_MODULE_ID
 - PAUDIO_MODULE_ID
 - audiosensors/PAUDIO_MODULE_ID
 - AUDIO_MODULE_ID
 - audiosensors/AUDIO_MODULE_ID
dev_langs:
 - c++
helpviewer_keywords:
 - _AUDIO_MODULE_ID
ai-usage: ai-assisted
---

## -description

The **AUDIO_MODULE_ID** structure provides a unique identification mechanism for audio modules within an audio device. This structure combines a class identifier and instance identifier to uniquely identify a specific audio module.

## -struct-fields

### -field ClassId

A **GUID** that identifies the audio module class. This GUID represents the type or category of the audio module, such as a specific type of audio processing unit, codec, or effect.

### -field InstanceId

A **ULONG** value that specifies the instance identifier of the audio module. This ID distinguishes between multiple instances of the same audio module class within a single audio device.

## -remarks

An audio module represents a distinct piece of audio processing logic that performs a relatively atomic function within an audio device. Audio modules may reside in the audio driver, audio DSP, or other audio processing hardware.

The **AUDIO_MODULE_ID** structure provides a two-level identification system:

1. The *ClassId* identifies the general type of audio module (e.g., "noise suppression module", "echo cancellation module", "amplifier module")
2. The *InstanceId* distinguishes between multiple instances of the same module class within a device

This identification scheme allows audio systems to precisely target specific audio processing components for configuration, control, or monitoring purposes.

This structure is used throughout the Audio Sensors Interface to identify which audio module is being operated on in function calls such as session management and buffer operations.

## -see-also

- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)
- [EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)
- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
- [audiosensors.h header](index.md)
