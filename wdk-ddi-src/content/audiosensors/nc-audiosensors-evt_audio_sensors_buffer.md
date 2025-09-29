---
UID: NC:audiosensors.EVT_AUDIO_SENSORS_BUFFER
tech.root: audio
title: EVT_AUDIO_SENSORS_BUFFER (audiosensors.h)
ms.date: 09/29/2025
targetos: Windows
description: The EVT_AUDIO_SENSORS_BUFFER callback function is used for buffer operations between audio and sensors drivers.
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
 - EVT_AUDIO_SENSORS_BUFFER
f1_keywords:
 - EVT_AUDIO_SENSORS_BUFFER
 - audiosensors/EVT_AUDIO_SENSORS_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_AUDIO_SENSORS_BUFFER
ai-usage: ai-generated
---

## -description

The **EVT_AUDIO_SENSORS_BUFFER** callback function is used for buffer operations between audio and sensors drivers. This callback has multiple uses including getting buffers, setting buffers, and submitting read reports.

## -parameters

### -param Context

A pointer to the audio sensors driver-supplied context.

### -param ModuleId

An [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md) structure that identifies the target audio module.

### -param SensorsSessionId

The session identifier returned by the [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md) callback. A value of 0 indicates a request that is not associated with any specific sensors session.

### -param BufferSize

A pointer to a ULONG that contains the size of the buffer in bytes. On input, this specifies the size of the buffer provided. On output, this may be updated to indicate the actual buffer size used or required.

### -param Buffer

An optional pointer to a proprietary buffer used for data exchange. The buffer size is specified by the **BufferSize** parameter.

## -returns

Returns an NTSTATUS value. Return **STATUS_SUCCESS** if the operation succeeds. Otherwise, return an appropriate [NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The **EVT_AUDIO_SENSORS_BUFFER** callback function type is used for three different buffer operations in the Audio Sensors Interface:

- **EvtAudioSensorsGetBuffer** - Used to retrieve buffer data from the audio sensors driver
- **EvtAudioSensorsSetBuffer** - Used to set buffer data in the audio sensors driver  
- **EvtAudioSensorsSubmitReadReport** - Used by the audio driver to submit read reports to the sensors driver

The specific operation depends on which function pointer in the [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md) structure is being used.

The **SensorsSessionId** parameter links operations to a specific sensor session created by **EVT_AUDIO_SENSORS_START_SESSION**. When the value is 0, the operation is not associated with any specific session.

## -see-also

- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
- [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)
- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)
