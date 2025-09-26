---
UID: NC:audiosensors.EVT_AUDIO_SENSORS_START_SESSION
tech.root: audio
title: EVT_AUDIO_SENSORS_START_SESSION
ms.date: 09/26/2025
targetos: Windows
description: The EVT_AUDIO_SENSORS_START_SESSION callback function is called to start a new audio sensors session with optional endpoint configurations.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: audiosensors.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - audiosensors.h
api_name:
 - EVT_AUDIO_SENSORS_START_SESSION
f1_keywords:
 - EVT_AUDIO_SENSORS_START_SESSION
 - audiosensors/EVT_AUDIO_SENSORS_START_SESSION
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_AUDIO_SENSORS_START_SESSION
ai-usage: ai-assisted
---

## -description

The **EVT_AUDIO_SENSORS_START_SESSION** callback function is implemented by audio sensor drivers to start a new sensors session. This function establishes a session for communication between the audio subsystem and sensor devices with optional endpoint configuration parameters.

## -parameters

### -param Context

[in] A pointer to the audio driver-supplied context that was passed to the interface when it was acquired.

### -param ModuleId

[in] An **[AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)** structure that identifies the specific audio module for which the session is being started.

### -param AudioRenderEndpointConfig

[in, optional] A pointer to an **[AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)** structure that contains configuration details for the audio render endpoint. This parameter can be **NULL** if no render endpoint configuration is required.

### -param AudioCaptureEndpointConfig

[in, optional] A pointer to an **[AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)** structure that contains configuration details for the audio capture endpoint. This parameter can be **NULL** if no capture endpoint configuration is required.

### -param SensorsSessionId

[out] A pointer to a **ULONG** that receives the non-zero session ID for the newly created sensors session. This session ID is used in subsequent calls to identify this session.

## -returns

Returns an **NTSTATUS** value that indicates the success or failure of the function call.

## -remarks

This callback function is called by the audio subsystem to initiate a new sensors session. The session allows for coordination between audio processing and sensor data, enabling advanced features such as adaptive audio processing based on environmental conditions, device usage patterns, or SoundWire bus topology changes.

The *AudioRenderEndpointConfig* and *AudioCaptureEndpointConfig* parameters provide optional configuration information for the audio endpoints that will be used during this session. These configurations may include technology-specific settings such as SDCA (SoundWire Device Class for Audio) function information, which specifies the SoundWire controller, link, device, and function addresses for proper bus communication.

For SDCA-based endpoints, the configuration structures may contain detailed topology information including:

- SoundWire controller and link identification
- SDCA device unique IDs and function numbers
- Function types (Smart Amplifier, Smart Microphone, etc.)
- Manufacturer and function-specific identifiers

The returned *SensorsSessionId* must be a non-zero value and will be used in subsequent operations such as buffer operations and session termination. The audio driver is responsible for managing session IDs and ensuring they remain valid until the corresponding **[EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)** is called.

## -see-also

- [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)
- [EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)
- [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)
- [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)
- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
- [audiosensors.h header](index.md)
