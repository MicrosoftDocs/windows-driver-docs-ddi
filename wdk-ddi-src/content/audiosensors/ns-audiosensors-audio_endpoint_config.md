---
UID: NS:audiosensors._AUDIO_ENDPOINT_CONFIG
tech.root: audio
title: AUDIO_ENDPOINT_CONFIG
ms.date: 09/26/2025
targetos: Windows
description: The AUDIO_ENDPOINT_CONFIG structure contains configuration information for audio endpoints used in audio sensors sessions.
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
ai-usage: ai-assisted
---

## -description

The **AUDIO_ENDPOINT_CONFIG** structure contains configuration information for audio endpoints that are used during audio sensors sessions. This structure provides a generic container for endpoint-specific configuration data that can accommodate different audio interface technologies, including traditional audio interfaces and modern digital audio buses such as SoundWire.

## -struct-fields

### -field Size

The size of the entire structure, including any additional audio technology-specific endpoint configuration data that follows the structure.

### -field Version

The version of this structure. This should be set to **AUDIO_ENDPOINT_CONFIG_VERSION_1**.

### -field AudioInterfaceType

A **GUID** that identifies the type of audio interface. This GUID determines how the additional configuration data (if any) should be interpreted. For example, **AUDIO_INTERFACE_SDCA** indicates that the configuration contains SDCA (SoundWire Device Class for Audio) specific information.

## -remarks

This structure serves as a header for audio endpoint configuration data. The actual configuration data may extend beyond this structure based on the *Size* field and the *AudioInterfaceType*. Different audio technologies may define their own extended versions of this structure by appending technology-specific fields after the base structure.

When *AudioInterfaceType* is set to **AUDIO_INTERFACE_SDCA**, the structure may be followed by SDCA-specific configuration data such as **[SDCA_ENDPOINT_CONFIG](ns-audiosensors-sdca_endpoint_config.md)**.

This structure is used as input parameters in the **[EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)** callback to configure both render and capture endpoints for a sensors session.

## -see-also

- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [SDCA_ENDPOINT_CONFIG](ns-audiosensors-sdca_endpoint_config.md)
- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
- [audiosensors.h header](index.md)
