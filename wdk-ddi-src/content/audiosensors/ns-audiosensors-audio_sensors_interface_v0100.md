---
UID: NS:audiosensors._AUDIO_SENSORS_INTERFACE_V0100
tech.root: audio
title: AUDIO_SENSORS_INTERFACE_V0100 (audiosensors.h)
ms.date: 10/02/2025
targetos: Windows
description: The AUDIO_SENSORS_INTERFACE_V0100 structure defines version 1.0 of the audio sensors interface, which provides communication between audio and sensors drivers.
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
ai-usage: ai-generated
---

## -description

The **AUDIO_SENSORS_INTERFACE_V0100** structure defines version 1.0 of the audio sensors interface. This interface enables communication between audio drivers and sensors drivers for presence sensing scenarios using ultrasound audio.

## -struct-fields

### -field InterfaceHeader

An **[INTERFACE](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface)** structure that contains standard interface information including size, version, and reference counting functions.

### -field EvtAudioSensorsStartSession

A pointer to the **[EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)** callback function that starts an audio sensors session.

### -field EvtAudioSensorsStopSession

A pointer to the **[EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)** callback function that stops an audio sensors session.

### -field EvtAudioSensorsGetBuffer

A pointer to the **[EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)** callback function that retrieves buffer data from the audio sensors driver.

### -field EvtAudioSensorsSetBuffer

A pointer to the **[EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)** callback function that sets buffer data in the audio sensors driver.

### -field EvtAudioSensorsSubmitReadReport

A pointer to the **[EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)** callback function used by the audio driver to submit read reports to the sensors driver.

## -remarks

This structure defines the complete audio sensors interface version 1.0. The interface is divided into two categories:

**Audio Sensors Driver to Audio Driver** - Functions that the audio driver calls:
- **EvtAudioSensorsStartSession** - Starts a sensor session
- **EvtAudioSensorsStopSession** - Stops a sensor session  
- **EvtAudioSensorsGetBuffer** - Gets buffer data from sensors driver
- **EvtAudioSensorsSetBuffer** - Sets buffer data in sensors driver

**Audio Driver to Audio Sensors Driver** - Functions that the sensors driver calls:
- **EvtAudioSensorsSubmitReadReport** - Submits read reports to sensors driver

The interface version is **AUDIO_SENSORS_INTERFACE_VERSION_0100** (0x0100).

## -see-also

- **[EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)**
- **[EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)**
- **[EVT_AUDIO_SENSORS_BUFFER](nc-audiosensors-evt_audio_sensors_buffer.md)**
- **[AUDIO_MODULE_ID](ns-audiosensors-audio_module_id.md)**
