---
UID: NC:audiosensors.EVT_AUDIO_SENSORS_BUFFER
tech.root: audio
title: EVT_AUDIO_SENSORS_BUFFER
ms.date: 09/26/2025
targetos: Windows
description: The EVT_AUDIO_SENSORS_BUFFER callback function is used to get, set, or submit buffer operations with audio sensors.
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
 - EVT_AUDIO_SENSORS_BUFFER
f1_keywords:
 - EVT_AUDIO_SENSORS_BUFFER
 - audiosensors/EVT_AUDIO_SENSORS_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_AUDIO_SENSORS_BUFFER
ai-usage: ai-assisted
---

## -description

The **EVT_AUDIO_SENSORS_BUFFER** callback function is implemented by audio sensor drivers to handle buffer operations. This callback is used for getting buffer data from sensors, setting buffer data to sensors, and submitting read reports.

## -parameters

### -param Context

[in] A pointer to the audio sensors driver-supplied context that was passed to the interface when it was acquired.

### -param ModuleId

[in] An **[AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)** structure that identifies the specific audio module.

### -param SensorsSessionId

[in] The session ID returned by a previous call to **[EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)**. A value of 0 indicates that the request is not associated with any specific sensors session.

### -param BufferSize

[in, out] On input, specifies the size of the buffer pointed to by the *Buffer* parameter. On output, receives the actual size of the data returned in the buffer.

### -param Buffer

[in, out] A pointer to a proprietary buffer used for the buffer operation. The meaning and format of this buffer is defined by the specific audio sensor implementation.

## -returns

Returns an **NTSTATUS** value that indicates the success or failure of the function call.

## -remarks

This callback function has multiple uses within the Audio Sensors Interface:

- **EvtAudioSensorsGetBuffer**: Used to retrieve buffer data from the audio sensor device
- **EvtAudioSensorsSetBuffer**: Used to send buffer data to the audio sensor device  
- **EvtAudioSensorsSubmitReadReport**: Used to submit read reports from the audio sensor device

The specific operation being performed depends on which function pointer in the **[AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)** structure is being called.

The *Buffer* parameter contains proprietary data whose format and meaning are defined by the audio driver and sensor device implementation. For SDCA (SoundWire Device Class for Audio) devices, this buffer may contain SDCA-specific control data, configuration parameters, or sensor readings that are used to optimize audio processing based on environmental conditions or device state.

The driver must ensure proper validation of buffer sizes and contents. When working with SoundWire/SDCA devices, the buffer operations may involve coordination with multiple SDCA functions across different devices on the SoundWire bus, requiring careful synchronization and error handling.

## -see-also

- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
- [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)
- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)
- [audiosensors.h header](index.md)
