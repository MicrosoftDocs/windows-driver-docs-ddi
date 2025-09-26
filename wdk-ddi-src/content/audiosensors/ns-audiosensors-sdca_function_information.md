---
UID: NS:audiosensors._SDCA_FUNCTION_INFORMATION
tech.root: audio
title: SDCA_FUNCTION_INFORMATION
ms.date: 09/26/2025
targetos: Windows
description: The SDCA_FUNCTION_INFORMATION structure contains information about a SoundWire Device Class for Audio (SDCA) function.
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
req.typenames: SDCA_FUNCTION_INFORMATION, *PSDCA_FUNCTION_INFORMATION
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
 - _SDCA_FUNCTION_INFORMATION
 - PSDCA_FUNCTION_INFORMATION
 - SDCA_FUNCTION_INFORMATION
f1_keywords:
 - _SDCA_FUNCTION_INFORMATION
 - audiosensors/_SDCA_FUNCTION_INFORMATION
 - PSDCA_FUNCTION_INFORMATION
 - audiosensors/PSDCA_FUNCTION_INFORMATION
 - SDCA_FUNCTION_INFORMATION
 - audiosensors/SDCA_FUNCTION_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _SDCA_FUNCTION_INFORMATION
ai-usage: ai-assisted
---

## -description

The **SDCA_FUNCTION_INFORMATION** structure contains information about a SoundWire Device Class for Audio (SDCA) function. SDCA is a standardized device class specification built on top of the MIPI SoundWire interface, providing a common framework for audio devices to interoperate across different vendors. This structure describes the configuration details of an SDCA function within the SoundWire bus topology, including its location on the bus and functional characteristics.

## -struct-fields

### -field Size

The size of the entire structure, in bytes.

### -field Version

The version of this structure. This should be set to **SDCA_FUNCTION_INFORMATION_VERSION_1**.

### -field FunctionNumber

The SDCA function number (0-7). This identifies the specific function within the SDCA device. Each SDCA peripheral device can support multiple functions, and this field specifies which function is being described.

### -field FunctionType

The SDCA function type. This specifies the type of audio function as defined by the SDCA specification, such as Smart Amplifier, Smart Microphone, Simple Amplifier, Simple Microphone, or other standardized function types.

### -field FunctionManufacturerId

The SDCA function manufacturer ID (16-bit value). This identifies the manufacturer of the specific SDCA function implementation and is used for vendor-specific extensions to the standard SDCA functionality.

### -field FunctionId

The SDCA function ID (16-bit value). This is a unique identifier assigned by the manufacturer to distinguish between different implementations of the same function type from the same vendor.

### -field ControllerId

The SoundWire controller ID (8-bit value). This identifies which SoundWire controller (master) this function is attached to in systems that have multiple SoundWire controllers.

### -field LinkId

The SoundWire link ID (8-bit value). This specifies which SoundWire link within the controller this function is attached to. Each SoundWire controller can manage multiple links.

### -field UniqueId

The SoundWire peripheral device's unique ID (8-bit value, range 1-11). This is the unique identifier assigned to the peripheral device on the SoundWire bus during enumeration, distinguishing it from other peripheral devices on the same link.

## -remarks

This structure is used as part of the Audio Sensors interface to provide detailed information about SDCA functions when configuring audio endpoints. The structure is typically used within the [**SDCA_ENDPOINT_CONFIG**](ns-audiosensors-sdca_endpoint_config.md) structure to specify multiple SDCA functions that need to be configured for a specific audio endpoint.

The SoundWire Device Class for Audio (SDCA) specification defines standardized audio functions and control mechanisms for SoundWire devices, enabling interoperability between different vendors' audio components. SDCA builds upon the MIPI SoundWire specification, which provides a scalable, low-power, multi-drop digital audio interface.

SoundWire supports up to 11 peripheral devices per link, with each device identified by a unique ID (1-11). The controller (master) manages the bus and coordinates data transfers with peripheral devices. The hierarchical addressing scheme (ControllerId → LinkId → UniqueId → FunctionNumber) allows precise identification of specific audio functions in complex, multi-controller audio systems.

This addressing information is essential for the audio subsystem to properly route control commands and audio data to the correct SDCA function within the SoundWire topology.

## -see-also

- [SDCA_ENDPOINT_CONFIG](ns-audiosensors-sdca_endpoint_config.md)
- [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)
- [EVT_AUDIO_SENSORS_START_SESSION](nc-audiosensors-evt_audio_sensors_start_session.md)
- [audiosensors.h header](index.md)
