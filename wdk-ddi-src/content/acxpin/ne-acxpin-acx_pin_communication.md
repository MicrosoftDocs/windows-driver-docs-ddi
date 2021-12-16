---
UID: NE:acxpin._ACX_PIN_COMMUNICATION
tech.root: audio
title: ACX_PIN_COMMUNICATION
ms.date: 12/15/2021
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

The **ACX_PIN_COMMUNICATION** enumeration is used by the [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md) structure to indicate the communication type of a pin.

## -enum-fields

### -field AcxPinCommunicationNone

Indicates that the pin is not used for communication.

### -field AcxPinCommunicationSink

TBD: Indicates that the pin is a sink.

### -field AcxPinCommunicationSource

TBD: Indicates that the pin is a source.

### -field AcxPinCommunicationMaximum

For internal validation, do not use.

## -remarks

## -see-also

- [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md)
