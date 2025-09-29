---
UID: NC:audiosensors.EVT_AUDIO_SENSORS_STOP_SESSION
tech.root: audio
title: EVT_AUDIO_SENSORS_STOP_SESSION (audiosensors.h)
ms.date: 09/29/2025
targetos: Windows
description: The EVT_AUDIO_SENSORS_STOP_SESSION callback function stops a previously started audio sensors session.
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
 - EVT_AUDIO_SENSORS_STOP_SESSION
f1_keywords:
 - EVT_AUDIO_SENSORS_STOP_SESSION
 - audiosensors/EVT_AUDIO_SENSORS_STOP_SESSION
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_AUDIO_SENSORS_STOP_SESSION
ai-usage: ai-generated
---

## -description

The **EVT_AUDIO_SENSORS_STOP_SESSION** callback function is implemented by the audio sensors driver and is called by the audio driver to stop a previously started sensors session.

## -parameters

### -param Context

A pointer to the audio driver-supplied context that was provided when the interface was obtained.

### -param ModuleId

An [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md) structure that identifies the target audio module for this operation.

### -param SensorsSessionId

The session identifier that was returned by the [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md) callback when the session was started.

## -returns

Returns an NTSTATUS value. Return **STATUS_SUCCESS** if the operation succeeds. Otherwise, return an appropriate [NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The **EVT_AUDIO_SENSORS_STOP_SESSION** callback is called by the audio driver when it needs to terminate a sensor session that was previously started with [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md).

After this function returns successfully, the **SensorsSessionId** is no longer valid and should not be used in subsequent operations.

The audio sensors driver should clean up any resources associated with the session and ensure that any active sensing operations are properly terminated.

## -see-also

- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)
- [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)
- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
