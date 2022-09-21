---
UID: NE:acxpin._ACX_PIN_QUALIFIER
tech.root: audio
title: ACX_PIN_QUALIFIER
ms.date: 03/25/2022
targetos: Windows
description: The ACX_PIN_QUALIFIER enumeration specify how the PIN is connected in the multi-circuit audio topology.
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
 - _ACX_PIN_QUALIFIER
 - PACX_PIN_QUALIFIER
 - ACX_PIN_QUALIFIER
f1_keywords:
 - _ACX_PIN_QUALIFIER
 - acxpin/_ACX_PIN_QUALIFIER
 - PACX_PIN_QUALIFIER
 - acxpin/PACX_PIN_QUALIFIER
 - ACX_PIN_QUALIFIER
 - acxpin/ACX_PIN_QUALIFIER
dev_langs:
 - c++
---

## -description

The **ACX_PIN_QUALIFIER** enumeration specify how the PIN is connected in the multi-circuit audio topology.

## -enum-fields

### -field AcxPinQualifierUnknown

Indicates that the pin qualifier is unknown.

### -field AcxPinQualifierBridgeA

Indicates composite support only. This pin is a bridge to another circuit on the streaming pin direction. This pin binds with AcxPinQualifierBridgeB pin type.

### -field AcxPinQualifierBridgeB

Indicates composite support only. This pin is a bridge to another circuit on the device pin direction. This pin binds with AcxPinQualifierBridgeA pin type.

### -field AcxPinQualifierBridgeDevice

Indicates composite support only.

### -field AcxPinQualifierMaximum

For internal validation, do not use.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxpin.h header](index.md)


