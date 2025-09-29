---
UID: NA:audiosensors
tech.root: audio
title: audiosensors.h
ms.date: 09/29/2025
targetos: Windows
description: The audiosensors.h header defines the types, constants, and functions for device drivers that advertise the Audio Sensors Interface.
prerelease: false
req.assembly:
req.construct-type: apiset
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
req.typenames:
req.type-library:
req.umdf-ver:
req.unicode-ansi:
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - audiosensors.h
api_name:
 - audiosensors
f1_keywords:
 - audiosensors
 - audiosensors/audiosensors
dev_langs:
 - c++
helpviewer_keywords:
 - audiosensors
ai-usage: ai-generated
---

## -description

This header defines the Audio Sensors Interface, which allows audio drivers to communicate with sensors drivers for presence sensing using ultrasound audio. The interface provides a standardized way for audio and sensors subsystems to coordinate for features like wake on approach and lock on leave.

## -remarks

The Audio Sensors Interface includes:

- Interface definition for communication between audio and sensors drivers
- Structure definitions for audio endpoint configuration 
- Callback functions for session management and buffer operations
- Support for SDCA (Smart Device Class Audio) endpoint configuration

The interface supports presence sensing scenarios where ultrasound audio signals are used to detect human presence near a device.

## -see-also

- [AUDIO_SENSORS_INTERFACE_V0100](ns-audiosensors-audio_sensors_interface_v0100.md)
- [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)
- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_STOP_SESSION](nc-audiosensors-evt_audio_sensors_stop_session.md)
