---
UID: NS:audiosensors._SDCA_FUNCTION_INFORMATION
tech.root: audio
title: SDCA_FUNCTION_INFORMATION (audiosensors.h)
ms.date: 09/29/2025
targetos: Windows
description: The SDCA_FUNCTION_INFORMATION structure provides detailed information about an SDCA (Smart Device Class Audio) function.
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
ai-usage: ai-generated
---

## -description

The **SDCA_FUNCTION_INFORMATION** structure provides detailed information about an SDCA (Smart Device Class Audio) function, including its location within the SoundWire topology and its functional characteristics.

## -struct-fields

### -field Size

The size, in bytes, of the entire structure.

### -field Version

The version of this structure. Must be set to **SDCA_FUNCTION_INFORMATION_VERSION_1** (1).

### -field FunctionNumber

The SDCA function number that identifies this specific function within the device.

### -field FunctionType

The SDCA function type that describes the category of functionality provided by this function.

### -field FunctionManufacturerId

The SDCA function manufacturer identifier, which identifies the vendor that created this function.

### -field FunctionId

The SDCA function identifier that uniquely identifies this function implementation from the manufacturer.

### -field ControllerId

The SoundWire controller identifier that this function is attached to.

### -field LinkId

The link identifier within the SoundWire controller that this function is attached to.

### -field UniqueId

The peripheral device's unique identifier within the SoundWire topology.

## -remarks

The **SDCA_FUNCTION_INFORMATION** structure is used within [SDCA_ENDPOINT_CONFIG](ns-audiosensors-sdca_endpoint_config.md) to describe the SDCA functions that need to be configured for audio sensor operations.

SDCA (Smart Device Class Audio) is a specification that defines how audio devices connect and operate over SoundWire interfaces. This structure provides the necessary addressing information to identify and configure specific SDCA functions within the SoundWire topology.

## -see-also

- [SDCA_ENDPOINT_CONFIG](ns-audiosensors-sdca_endpoint_config.md)
- [AUDIO_ENDPOINT_CONFIG](ns-audiosensors-audio_endpoint_config.md)
