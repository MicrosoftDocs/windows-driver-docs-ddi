---
UID: NS:acxpin._ACX_MICROPHONE_CONFIG
tech.root: audio
title: ACX_MICROPHONE_CONFIG
ms.date: 10/05/2021
targetos: Windows
description: The ACX_MICROPHONE_CONFIG structure allows the driver to specify the properties of a microphone.
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

The ACX_MICROPHONE_CONFIG structure allows the driver to specify the properties of a microphone.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Flags

Flags from [ACX_MICROPHONE_CONFIG_FLAG](ne-acxpin-acx_microphone_config_flags.md) to use in creation.

### -field MicrophoneSnrDB

The microphone signal to noise ratio (SNR) measured in dB units.

### -field MicrophoneSensitivityDB

 The microphone sensitivity in decibels relative to full scale (dBFS) units including any hardware gain. This value includes any hardware integration that impacts mic sensitivity, prior to any software gain. The MicrophoneSensitivityDB value does not include any software gain that is applied from the audio stack.

### -field MicArrayGeometry

An optional ACXMICARRAYGEOMETRY object that specifies the geometry of the microphone if it is a microphone array.

### -field InterleavedFormat

An optional pointer to an [ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION](ns-acxpin-acx_interleaved_audio_format_information.md) structure for the microphone.

## -remarks

The ACX_MICROPHONE_CONFIG structure should be assigned to the MicrophoneConfig member of the [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md) structure and AcxPinConfigMicrophoneConfigSpecified should be included in the Flags member of the ACX_PIN_CONFIG structure.

To initialize an ACX_MICROPHONE_CONFIG structure, your driver should call [ACX_MICROPHONE_CONFIG_INIT](nf-acxpin-acx_microphone_config_init.md).

## -see-also

[ACX_MICROPHONE_CONFIG_INIT](nf-acxpin-acx_microphone_config_init.md)
[AcxMicArrayGeometryCreate](nf-acxpin-acxmicarraygeometrycreate.md)
[ACX_INTERLEAVED_AUDIO_FORMAT_INFORMATION](ns-acxpin-acx_interleaved_audio_format_information.md)

READY2GO
