---
UID: NS:audiosensors._SDCA_ENDPOINT_CONFIG
tech.root: audio
title: SDCA_ENDPOINT_CONFIG (audiosensors.h)
ms.date: 09/29/2025
targetos: Windows
description: The SDCA_ENDPOINT_CONFIG structure defines the configuration for SDCA (Smart Device Class Audio) endpoints, including information about the SDCA functions that need to be configured.
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
req.typenames: SDCA_ENDPOINT_CONFIG, *PSDCA_ENDPOINT_CONFIG
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
 - _SDCA_ENDPOINT_CONFIG
 - PSDCA_ENDPOINT_CONFIG
 - SDCA_ENDPOINT_CONFIG
f1_keywords:
 - _SDCA_ENDPOINT_CONFIG
 - audiosensors/_SDCA_ENDPOINT_CONFIG
 - PSDCA_ENDPOINT_CONFIG
 - audiosensors/PSDCA_ENDPOINT_CONFIG
 - SDCA_ENDPOINT_CONFIG
 - audiosensors/SDCA_ENDPOINT_CONFIG
dev_langs:
 - c++
helpviewer_keywords:
 - _SDCA_ENDPOINT_CONFIG
ai-usage: ai-generated
---

## -description

The **SDCA_ENDPOINT_CONFIG** structure defines the configuration for SDCA (Smart Device Class Audio) endpoints. This structure contains an array of SDCA function information that describes the functions that need to be configured for the endpoint.

## -struct-fields

### -field Size

The size, in bytes, of the entire structure including the size of the **SdcaFunctionInformation** array.

### -field Version

The version of this structure. Must be set to **SDCA_ENDPOINT_CONFIG_VERSION_1** (1).

### -field SdcaFunctionInformationCount

The number of SDCA functions in the **SdcaFunctionInformation** array.

### -field SdcaFunctionInformation[ANYSIZE_ARRAY]

An array of [SDCA_FUNCTION_INFORMATION](ns-audiosensors-sdca_function_information.md) structures that provide details about the SDCA functions that need to be configured for this endpoint.

## -remarks

The **SDCA_ENDPOINT_CONFIG** structure is a variable-length structure that follows an [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md) structure when the **AudioInterfaceType** is **AUDIO_INTERFACE_SDCA**.

SDCA (Smart Device Class Audio) is a specification for audio devices that operate over SoundWire interfaces. This structure allows configuration of multiple SDCA functions that collectively implement an audio endpoint for sensor operations.

## -see-also

- [SDCA_FUNCTION_INFORMATION](ns-audiosensors-sdca_function_information.md)
- [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)
- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
