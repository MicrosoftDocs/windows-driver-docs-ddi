---
UID: NE:acxpin._ACX_MICROPHONE_TYPE
tech.root: audio
title: ACX_MICROPHONE_TYPE
ms.date: 07/22/2022
targetos: Windows
description: The ACX_MICROPHONE_TYPE enumeration is used to identify the pickup pattern of a microphone.
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
 - _ACX_MICROPHONE_TYPE
 - ACX_MICROPHONE_TYPE
f1_keywords:
 - _ACX_MICROPHONE_TYPE
 - acxpin/_ACX_MICROPHONE_TYPE
 - ACX_MICROPHONE_TYPE
 - acxpin/ACX_MICROPHONE_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_MICROPHONE_TYPE** enumeration is used to identify the pickup pattern of a microphone.

## -enum-fields

### -field AcxMicrophoneTypeOmniDirectional

Indicates that the microphone has an omnidirectional pickup pattern.

### -field AcxMicrophoneTypeSubCardioid

Indicates that the microphone has a subcardioid pickup pattern. Subcardioid is also known as wide cardioid.

### -field AcxMicrophoneTypeCardioid

Indicates that the microphone has a cardioid pickup pattern.

### -field AcxMicrophoneTypeSuperCardioid

Indicates that the microphone has a super-cardioid pickup pattern.

### -field AcxMicrophoneTypeHyperCardioid

Indicates that the microphone has a hyper-cardioid pickup pattern.

### -field AcxMicrophoneType8Shaped

Indicates that the microphone has an eight-shaped pickup pattern.

### -field AcxMicrophoneTypeMaximum

For internal validation, do not use.

### -field AcxMicrophoneTypeVendorDefined

Indicates that the microphone pickup pattern is vendor defined.

## -remarks

## -see-also

- [acxpin.h header](index.md)


