---
UID: NC:audiosensors.EVT_AUDIO_SENSORS_START_SESSION
tech.root: audio
title: EVT_AUDIO_SENSORS_START_SESSION (audiosensors.h)
ms.date: 09/29/2025
targetos: Windows
description: The EVT_AUDIO_SENSORS_START_SESSION callback function starts an audio sensors session with optional render and capture endpoint configurations.
prerelease: false
req.assembly:
req.construct-type: function
req.ddi-compliance:
req.dll:
req.header: audiosensors.h
req.idl:
req.include-header:
req.irql: PASSIVE_LEVEL
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
ai-usage: ai-generated
---

## -description

The **EVT_AUDIO_SENSORS_START_SESSION** callback function is implemented by the audio sensors driver and is called by the audio driver to start a new sensors session. This function configures audio endpoints for use in presence sensing scenarios.

## -parameters

### -param Context

A pointer to the audio driver-supplied context that was provided when the interface was obtained.

### -param ModuleId

An [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md) structure that identifies the target audio module for this session.

### -param AudioRenderEndpointConfig

An optional pointer to an [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md) structure that contains the audio render endpoint configuration details to be used for this session. This parameter can be NULL if no render endpoint configuration is needed.

### -param AudioCaptureEndpointConfig

An optional pointer to an [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md) structure that contains the audio capture endpoint configuration details to be used for this session. This parameter can be NULL if no capture endpoint configuration is needed.

### -param SensorsSessionId

A pointer to a ULONG that receives a non-zero session identifier returned by the audio sensors driver. This identifier is used in subsequent calls to identify this specific session.

## -returns

Returns an NTSTATUS value. Return **STATUS_SUCCESS** if the operation succeeds. Otherwise, return an appropriate [NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The **EVT_AUDIO_SENSORS_START_SESSION** callback is called by the audio driver when it needs to start a sensor session for presence sensing operations. The session associates audio endpoints with sensor functionality, typically for ultrasound-based presence detection.

The **SensorsSessionId** returned by this function must be a non-zero value that uniquely identifies the session. This identifier is used in subsequent calls to [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md) and [EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md) functions.

Both **AudioRenderEndpointConfig** and **AudioCaptureEndpointConfig** are optional, allowing flexibility in configuring sessions that may only need one direction of audio flow.

## -see-also

- [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)
- [EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)
- [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)
- [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)
- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
