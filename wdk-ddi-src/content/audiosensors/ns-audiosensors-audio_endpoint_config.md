---
UID: NS:audiosensors._AUDIO_ENDPOINT_CONFIG
tech.root: audio
title: AUDIO_ENDPOINT_CONFIG (audiosensors.h)
ms.date: 09/29/2025
targetos: Windows
description: The AUDIO_ENDPOINT_CONFIG structure defines the configuration for an audio endpoint, including the audio interface type and additional configuration data.
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
req.typenames: AUDIO_ENDPOINT_CONFIG, *PAUDIO_ENDPOINT_CONFIG
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
 - _AUDIO_ENDPOINT_CONFIG
 - PAUDIO_ENDPOINT_CONFIG
 - AUDIO_ENDPOINT_CONFIG
f1_keywords:
 - _AUDIO_ENDPOINT_CONFIG
 - audiosensors/_AUDIO_ENDPOINT_CONFIG
 - PAUDIO_ENDPOINT_CONFIG
 - audiosensors/PAUDIO_ENDPOINT_CONFIG
 - AUDIO_ENDPOINT_CONFIG
 - audiosensors/AUDIO_ENDPOINT_CONFIG
dev_langs:
 - c++
helpviewer_keywords:
 - _AUDIO_ENDPOINT_CONFIG
ai-usage: ai-generated
---

## -description

The **AUDIO_ENDPOINT_CONFIG** structure defines the configuration for an audio endpoint used in sensor sessions. This structure provides information about the audio interface type and allows for additional technology-specific configuration data.

## -struct-fields

### -field Size

The size, in bytes, of the entire structure including any additional audio technology-specific endpoint configuration bytes that follow this structure.

### -field Version

The version of this structure. Must be set to **AUDIO_ENDPOINT_CONFIG_VERSION_1** (1).

### -field AudioInterfaceType

A GUID that identifies the audio interface type. For SDCA interfaces, use **AUDIO_INTERFACE_SDCA**. This GUID determines the format of any additional configuration data that follows this structure.

## -remarks

The **AUDIO_ENDPOINT_CONFIG** structure is a variable-length structure. Additional bytes following this structure provide audio interface-specific endpoint configuration. When **AudioInterfaceType** is **AUDIO_INTERFACE_SDCA**, the bytes following this structure will contain a [SDCA_ENDPOINT_CONFIG](ns-audiosensors-sdca_endpoint_config.md) structure.

This structure is used when starting audio sensor sessions to specify the configuration for render and capture endpoints.

## -see-also

- [SDCA_ENDPOINT_CONFIG](ns-audiosensors-sdca_endpoint_config.md)
- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
