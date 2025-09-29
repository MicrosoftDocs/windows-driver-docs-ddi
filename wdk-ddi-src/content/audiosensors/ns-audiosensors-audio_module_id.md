---
UID: NS:audiosensors._AUDIO_MODULE_ID
tech.root: audio
title: AUDIO_MODULE_ID (audiosensors.h)
ms.date: 09/29/2025
targetos: Windows
description: The AUDIO_MODULE_ID structure identifies a specific audio module by its class and instance identifiers.
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
ai-usage: ai-generated
---

## -description

The **AUDIO_MODULE_ID** structure identifies a specific audio module by its class and instance identifiers. This structure is used to target operations to a particular audio module within the audio system.

## -struct-fields

### -field ClassId

A GUID that identifies the audio module class. This provides the type classification for the audio module.

### -field InstanceId

A ULONG value that represents the instance identifier for the audio module. This distinguishes between multiple instances of the same audio module class.

## -remarks

The **AUDIO_MODULE_ID** structure is used throughout the Audio Sensors Interface to specify which audio module should be the target of various operations, such as starting or stopping sensor sessions and managing buffers.

The combination of **ClassId** and **InstanceId** must uniquely identify an audio module within the system.

## -see-also

- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)
- [EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)
