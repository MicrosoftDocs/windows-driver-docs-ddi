---
UID: NE:acxpin._ACX_PIN_TYPE
tech.root: audio
title: ACX_PIN_TYPE
ms.date: 02/17/2022
targetos: Windows
description: The ACX_PIN_TYPE enumeration is used by the ACX_PIN_CONFIG structure to indicate the type of a pin.
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
 - _ACX_PIN_TYPE
 - PACX_PIN_TYPE
 - ACX_PIN_TYPE
f1_keywords:
 - _ACX_PIN_TYPE
 - acxpin/_ACX_PIN_TYPE
 - PACX_PIN_TYPE
 - acxpin/PACX_PIN_TYPE
 - ACX_PIN_TYPE
 - acxpin/ACX_PIN_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_PIN_TYPE** enumeration is used by the [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md) structure to indicate the type of a pin.

## -enum-fields

### -field AcxPinTypeOther

Indicates that the pin type is not a sink nor a source.

### -field AcxPinTypeSink

Indicates that the pin type is a sink.

### -field AcxPinTypeSource

Indicates that the pin type is a source.

### -field AcxPinTypeMaximum

For internal validation, do not use.

## -remarks

## -see-also

- [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md)
- [ACX_PIN_CONFIG_INIT](nf-acxpin-acx_pin_config_init.md)
- [AcxPinGetType](nf-acxpin-acxpingettype.md)

READY2GO
