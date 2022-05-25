---
UID: NE:sensorsdef.HUMAN_PRESENCE_DETECTION_TYPE
tech.root: The HUMAN_PRESENCE_DETECTION_TYPE enumeration values indicate types of human presence detection hardware.
title: HUMAN_PRESENCE_DETECTION_TYPE
ms.date: 02/09/2022
targetos: Windows
description: The HUMAN_PRESENCE_DETECTION_TYPE enumeration values indicate types of human presence detection hardware.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: sensorsdef.h
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
 - sensorsdef.h
api_name:
 - HUMAN_PRESENCE_DETECTION_TYPE
f1_keywords:
 - HUMAN_PRESENCE_DETECTION_TYPE
 - sensorsdef/HUMAN_PRESENCE_DETECTION_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - HUMAN_PRESENCE_DETECTION_TYPE
---

## -description

The **HUMAN_PRESENCE_DETECTION_TYPE** enumeration values indicate types of human presence detection hardware.

## -enum-fields

### -field HumanPresenceDetectionType_VendorDefinedNonBiometric

Indicates a vendor defined, non-biometric human presence detection type.

### -field HumanPresenceDetectionType_VendorDefinedBiometric

Indicates a vendor defined, biometric human presence detection type.

### -field HumanPresenceDetectionType_FacialBiometric

Indicates a facial human presence detection type, such as a camera.

### -field HumanPresenceDetectionType_AudioBiometric

Indicates an audio human presence detection type, such as a microphone.

### -field HumanPresenceDetectionType_Force_Dword

Used to force the **HUMAN_PRESENCE_DETECTION_TYPE** enum to a 32-bit data type (a DWORD).

## -remarks

## -see-also

- [HUMAN_PRESENCE_DETECTION_TYPE_COUNT](ne-sensorsdef-human_presence_detection_type_count.md)
