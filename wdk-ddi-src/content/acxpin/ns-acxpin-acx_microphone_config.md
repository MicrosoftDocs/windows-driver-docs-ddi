---
UID: NS:acxpin._ACX_MICROPHONE_CONFIG
tech.root: audio
title: ACX_MICROPHONE_CONFIG
ms.date: 07/22/2022
targetos: Windows
description: The ACX_MICROPHONE_CONFIG structure is used to configure a microphone.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_MICROPHONE_CONFIG, *PACX_MICROPHONE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_MICROPHONE_CONFIG
 - PACX_MICROPHONE_CONFIG
 - ACX_MICROPHONE_CONFIG
f1_keywords:
 - _ACX_MICROPHONE_CONFIG
 - acxpin/_ACX_MICROPHONE_CONFIG
 - PACX_MICROPHONE_CONFIG
 - acxpin/PACX_MICROPHONE_CONFIG
 - ACX_MICROPHONE_CONFIG
 - acxpin/ACX_MICROPHONE_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_MICROPHONE_CONFIG** structure is used to configure a microphone.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_MICROPHONE_CONFIG** structure in bytes.

### -field Flags

A combination of values from the [ACX_MICROPHONE_CONFIG_FLAGS](ne-acxpin-acx_microphone_config_flags.md) enum that describe the microphone.

### -field MicrophoneSnrDB

A 16.16 fixed point decibel (dB) value specifying the microphone's signal-to-noise ratio. Setting this to LONG_MIN_VALUE means that this field is unsupported.

### -field MicrophoneSensitivityDB

A 16.16 fixed point decibel (dB) value specifying the microphone's sensitivity. Setting this to LONG_MIN_VALUE means that this field is unsupported.

### -field MicArrayGeometry

An optional [ACX_MIC_ARRAY_GEOMETRY](ns-acxpin-acx_mic_array_geometry.md) structure that describes the geometry of the microphone if it is a microphone array.

### -field InterleavedFormat

An optional pointer to an [ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION](ns-acxpin-acx_interleaved_audio_format_information.md) structure that specifies how loopback audio is interleaved with the microphone audio.

## -remarks

The ACX_MICROPHONE_CONFIG structure should be assigned to the MicrophoneConfig member of the [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md) structure and AcxPinConfigMicrophoneConfigSpecified should be included in the Flags member of the ACX_PIN_CONFIG structure.

To initialize an ACX_MICROPHONE_CONFIG structure, your driver should call [ACX_MICROPHONE_CONFIG_INIT](nf-acxpin-acx_microphone_config_init.md).

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_MICROPHONE_CONFIG_FLAGS](ne-acxpin-acx_microphone_config_flags.md)
- [ACX_MIC_ARRAY_GEOMETRY](ns-acxpin-acx_mic_array_geometry.md)
- [acxpin.h header](index.md)


