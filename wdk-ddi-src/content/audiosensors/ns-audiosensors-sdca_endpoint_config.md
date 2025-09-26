---
UID: NS:audiosensors._SDCA_ENDPOINT_CONFIG
tech.root: audio
title: SDCA_ENDPOINT_CONFIG
ms.date: 09/26/2025
targetos: Windows
description: The SDCA_ENDPOINT_CONFIG structure contains configuration information for SoundWire Device Class for Audio (SDCA) endpoints.
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
ai-usage: ai-assisted
---

## -description

The **SDCA_ENDPOINT_CONFIG** structure contains configuration information for SoundWire Device Class for Audio (SDCA) endpoints. This structure specifies the SDCA functions that need to be configured for a particular audio endpoint, allowing the audio subsystem to properly initialize and manage SDCA devices on the SoundWire bus.

## -struct-fields

### -field Size

The size of the entire structure, including the size of the **SdcaFunctionInformation** array. This field allows for proper parsing of the variable-length structure.

### -field Version

The version of this structure. This should be set to **SDCA_ENDPOINT_CONFIG_VERSION_1**.

### -field SdcaFunctionInformationCount

The number of SDCA function information structures contained in the **SdcaFunctionInformation** array. This count determines how many SDCA functions need to be configured for this endpoint.

### -field SdcaFunctionInformation[ANYSIZE_ARRAY]

An array of **[SDCA_FUNCTION_INFORMATION](ns-audiosensors-sdca_function_information.md)** structures that provide details about the SDCA functions that need to be configured. The actual size of this array is determined by the **SdcaFunctionInformationCount** field.

## -remarks

This structure is used to configure SDCA (SoundWire Device Class for Audio) endpoints within the audio sensors interface. SDCA is a standardized approach for audio devices on the SoundWire bus, providing interoperability between different vendors' audio components while leveraging the low-power, scalable characteristics of the MIPI SoundWire digital audio interface.

The structure contains a variable-length array of SDCA function information. Each entry in the **SdcaFunctionInformation** array describes a specific SDCA function that must be configured, including details such as the function number, type, manufacturer ID, and SoundWire bus topology information (controller ID, link ID, and unique device ID).

Multiple SDCA functions may need to be configured for a single audio endpoint if the endpoint requires coordination between different SDCA devices or different functions within the same SDCA device. For example, a smart speaker endpoint might require configuration of both amplifier and microphone functions.

When this structure is used as part of an **[AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)**, it provides the SDCA-specific configuration data needed to properly set up the audio endpoint for communication with SDCA devices on the SoundWire bus.

## -see-also

- [SDCA_FUNCTION_INFORMATION](ns-audiosensors-sdca_function_information.md)
- [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)
- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [audiosensors.h header](index.md)
