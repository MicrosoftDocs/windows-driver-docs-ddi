---
UID: NS:audiosensors._AUDIO_SENSORS_INTERFACE_V0100
tech.root: audio
title: AUDIO_SENSORS_INTERFACE_V0100
ms.date: 09/26/2025
targetos: Windows
description: The AUDIO_SENSORS_INTERFACE_V0100 structure defines the Audio Sensors Interface version 1.0, which provides communication between audio drivers and audio sensor devices.
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
req.typenames: AUDIO_SENSORS_INTERFACE_V0100, *PAUDIO_SENSORS_INTERFACE_V0100
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
 - _AUDIO_SENSORS_INTERFACE_V0100
 - PAUDIO_SENSORS_INTERFACE_V0100
 - AUDIO_SENSORS_INTERFACE_V0100
f1_keywords:
 - _AUDIO_SENSORS_INTERFACE_V0100
 - audiosensors/_AUDIO_SENSORS_INTERFACE_V0100
 - PAUDIO_SENSORS_INTERFACE_V0100
 - audiosensors/PAUDIO_SENSORS_INTERFACE_V0100
 - AUDIO_SENSORS_INTERFACE_V0100
 - audiosensors/AUDIO_SENSORS_INTERFACE_V0100
dev_langs:
 - c++
helpviewer_keywords:
 - _AUDIO_SENSORS_INTERFACE_V0100
ai-usage: ai-assisted
---

## -description

The **AUDIO_SENSORS_INTERFACE_V0100** structure defines the Audio Sensors Interface version 1.0. This interface provides a standardized communication mechanism between audio drivers and audio sensor devices, enabling advanced audio processing capabilities that can adapt based on sensor data, environmental conditions, and modern audio bus technologies such as SoundWire Device Class for Audio (SDCA).

## -struct-fields

### -field InterfaceHeader

An **[INTERFACE](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface)** structure that contains the standard interface header information, including the interface type, size, version, and reference/dereference functions.

### -field EvtAudioSensorsStartSession

A pointer to the driver's **[EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)** callback function. This function is called to start a new audio sensors session with specified endpoint configurations.

### -field EvtAudioSensorsStopSession

A pointer to the driver's **[EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)** callback function. This function is called to stop an active audio sensors session.

### -field EvtAudioSensorsGetBuffer

A pointer to the driver's **[EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)** callback function used for retrieving buffer data from the audio sensor device.

### -field EvtAudioSensorsSetBuffer

A pointer to the driver's **[EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)** callback function used for sending buffer data to the audio sensor device.

### -field EvtAudioSensorsSubmitReadReport

A pointer to the driver's **[EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)** callback function used for submitting read reports from the audio sensor device.

## -remarks

This interface structure is used to establish communication between audio drivers and sensor devices that can provide contextual information to enhance audio processing. Examples of such sensors might include ambient light sensors, proximity sensors, or accelerometers that can influence audio behavior based on device usage patterns or environmental conditions.

The interface version is defined by **AUDIO_SENSORS_INTERFACE_VERSION_0100**, which has a value of 0x0100, indicating version 1.0 of the interface.

Drivers that implement this interface must provide implementations for all the callback functions defined in the structure. The interface follows the standard Windows interface pattern with proper reference counting through the **InterfaceHeader**.

## -see-also

- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)
- [EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)
- [AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)
- [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)
- [audiosensors.h header](index.md)
