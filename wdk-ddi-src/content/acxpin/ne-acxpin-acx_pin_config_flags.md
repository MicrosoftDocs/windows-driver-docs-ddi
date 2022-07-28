---
UID: NE:acxpin._ACX_PIN_CONFIG_FLAGS
tech.root: audio
title: ACX_PIN_CONFIG_FLAGS
ms.date: 03/25/2022
targetos: Windows
description: The ACX_PIN_CONFIG_FLAGS enumeration specifies PIN configuration settings used within the ACX_PIN_CONFIG structure.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_PIN_CONFIG_FLAGS
 - ACX_PIN_CONFIG_FLAGS
f1_keywords:
 - _ACX_PIN_CONFIG_FLAGS
 - acxpin/_ACX_PIN_CONFIG_FLAGS
 - ACX_PIN_CONFIG_FLAGS
 - acxpin/ACX_PIN_CONFIG_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_PIN_CONFIG_FLAGS** enumeration specifies PIN configuration settings used within the ACX_PIN_CONFIG structure.

## -enum-fields

### -field AcxPinConfigNoFlags

Indicates that there are no flags set.

### -field AcxPinConfigMicrophoneConfigSpecified

Indicates that an [ACX_MICROPHONE_CONFIG](ns-acxpin-acx_microphone_config.md) structure is available for this PIN.

### -field AcxPinConfigValidFlags

For internal validation, do not use.

## -remarks

## -see-also

- [ACX_MICROPHONE_CONFIG](ns-acxpin-acx_microphone_config.md)
- [acxpin.h header](index.md)
 

