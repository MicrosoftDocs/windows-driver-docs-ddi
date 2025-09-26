---
UID: NC:audiosensors.EVT_AUDIO_SENSORS_STOP_SESSION
tech.root: audio
title: EVT_AUDIO_SENSORS_STOP_SESSION
ms.date: 09/26/2025
targetos: Windows
description: The EVT_AUDIO_SENSORS_STOP_SESSION callback function is called to stop an active audio sensors session.
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
 - EVT_AUDIO_SENSORS_STOP_SESSION
f1_keywords:
 - EVT_AUDIO_SENSORS_STOP_SESSION
 - audiosensors/EVT_AUDIO_SENSORS_STOP_SESSION
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_AUDIO_SENSORS_STOP_SESSION
ai-usage: ai-assisted
---

## -description

The **EVT_AUDIO_SENSORS_STOP_SESSION** callback function is implemented by audio sensor drivers to terminate an active sensors session. This function cleans up resources and stops communication between the audio subsystem and sensor devices for the specified session.

## -parameters

### -param Context

[in] A pointer to the audio driver-supplied context that was passed to the interface when it was acquired.

### -param ModuleId

[in] An **[AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)** structure that identifies the specific audio module for which the session is being stopped.

### -param SensorsSessionId

[in] The session ID that was returned by a previous call to **[EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)**. This identifies the specific session to be terminated.

## -returns

Returns an **NTSTATUS** value that indicates the success or failure of the function call.

## -remarks

This callback function is called by the audio subsystem to terminate a sensors session that was previously started with **[EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)**. The driver should clean up any resources associated with the specified session and ensure that no further operations occur for that session ID.

After this function returns successfully, the *SensorsSessionId* becomes invalid and should not be used in any subsequent operations. Any pending buffer operations or other session-related activities should be completed or cancelled before the session is terminated.

The driver must ensure proper cleanup of all resources allocated for the session, including any internal buffers, configuration settings, or hardware states that were established during the session.

## -see-also

- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)
- [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)
- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
- [audiosensors.h header](index.md)
