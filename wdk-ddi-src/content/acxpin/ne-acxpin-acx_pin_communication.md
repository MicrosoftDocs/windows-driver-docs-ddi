---
UID: NE:acxpin._ACX_PIN_COMMUNICATION
tech.root: audio
title: ACX_PIN_COMMUNICATION
ms.date: 03/25/2022
targetos: Windows
description: The ACX_PIN_COMMUNICATION enumeration is used by the ACX_PIN_CONFIG structure to indicate the communication type of a pin.
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
 - _ACX_PIN_COMMUNICATION
 - PACX_PIN_COMMUNICATION
 - ACX_PIN_COMMUNICATION
f1_keywords:
 - _ACX_PIN_COMMUNICATION
 - acxpin/_ACX_PIN_COMMUNICATION
 - PACX_PIN_COMMUNICATION
 - acxpin/PACX_PIN_COMMUNICATION
 - ACX_PIN_COMMUNICATION
 - acxpin/ACX_PIN_COMMUNICATION
dev_langs:
 - c++
---

## -description

The **ACX_PIN_COMMUNICATION** enumeration is used by the [ACX_PIN_CONFIG](..\acxpin\ns-acxpin-acx_pin_config.md) structure to indicate the communication type of a pin.

## -enum-fields

### -field AcxPinCommunicationNone

Indicates that the pin is not used for communication.

### -field AcxPinCommunicationSink

Indicates that the pin is a communication sink.

### -field AcxPinCommunicationSource

Indicates that the pin is a communication source.

### -field AcxPinCommunicationMaximum

For internal validation, do not use.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md)
- [ACX_PIN_CONFIG_INIT](nf-acxpin-acx_pin_config_init.md)
- [acxpin.h header\]\(index.md\)
