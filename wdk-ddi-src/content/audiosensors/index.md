---
UID: NA:audiosensors
tech.root: audio
title: audiosensors
ms.date: 09/19/2025
targetos: Windows
description: The audiosensors.h header defines types, constants, and functions for device drivers that advertise Audio Sensors Interface.
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
---

## -description

The **audiosensors.h** header defines the types, constants, and functions that are exposed to device drivers that advertise Audio Sensors Interface. This header enables support for SoundWire Device Class for Audio (SDCA) speaker aggregation and ultrasound support.

The Audio Sensors Interface provides communication between audio drivers and audio sensors drivers, allowing for enhanced audio processing and sensor data integration.

## -remarks

The Audio Sensors Interface supports the following key functionality:

- Starting and stopping sensor sessions with audio endpoint configuration
- Buffer management for sensor data exchange
- Support for SoundWire Device Class for Audio (SDCA) configurations
- Integration with audio module identification

The interface class GUID for Audio Sensors Interface is:

```cpp
// {00E6037C-59D1-4890-8CD8-E090891A250C}
DEFINE_GUID(AUDIO_SENSORS_INTERFACE, 0xe6037c, 0x59d1, 0x4890, 0x8c, 0xd8, 0xe0, 0x90, 0x89, 0x1a, 0x25, 0xc);
```

## -see-also

- [AUDIO_ENDPOINT_CONFIG structure](ns-audiosensors-audio_endpoint_config.md)
- [AUDIO_MODULE_ID structure](ns-audiosensors-audio_module_id.md)
- [AUDIO_SENSORS_INTERFACE_V0100 structure](ns-audiosensors-audio_sensors_interface_v0100.md)
- [SDCA_ENDPOINT_CONFIG structure](ns-audiosensors-sdca_endpoint_config.md)
- [SDCA_FUNCTION_INFORMATION structure](ns-audiosensors-sdca_function_information.md)
- [EVT_AUDIO_SENSORS_BUFFER callback function](nc-audiosensors-evt_audio_sensors_buffer.md)
- [EVT_AUDIO_SENSORS_START_SESSION callback function](nc-audiosensors-evt_audio_sensors_start_session.md)
- [EVT_AUDIO_SENSORS_STOP_SESSION callback function](nc-audiosensors-evt_audio_sensors_stop_session.md)
