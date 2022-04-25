---
UID: NS:acxpin._ACX_MICROPHONE_COORDINATES
tech.root: audio
title: ACX_MICROPHONE_COORDINATES
ms.date: 02/24/2022
targetos: Windows
description: The ACX_MICROPHONE_COORDINATES structure specifies the 3D location of the microphone in X, Y, and Z coordinates.
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
req.typenames: ACX_MICROPHONE_COORDINATES, *PACX_MICROPHONE_COORDINATES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_MICROPHONE_COORDINATES
 - PACX_MICROPHONE_COORDINATES
 - ACX_MICROPHONE_COORDINATES
f1_keywords:
 - _ACX_MICROPHONE_COORDINATES
 - acxpin/_ACX_MICROPHONE_COORDINATES
 - PACX_MICROPHONE_COORDINATES
 - acxpin/PACX_MICROPHONE_COORDINATES
 - ACX_MICROPHONE_COORDINATES
 - acxpin/ACX_MICROPHONE_COORDINATES
dev_langs:
 - c++
---

## -description

The **ACX_MICROPHONE_COORDINATES** structure specifies the 3D location of the microphone in X, Y, and Z coordinates.

## -struct-fields

### -field Type

A value from the [ACX_MICROPHONE_TYPE](ne-acxpin-acx_microphone_type.md) enum that identifies the pickup pattern of the microphone.

### -field XCoord

The X coordinate of the microphone.

### -field YCoord

The Y coordinate of the microphone.

### -field ZCoord

The Z coordinate of the microphone.

### -field VerticalAngle

The MRA vertical angle of the microphone

### -field HorizontalAngle

The MRA horizontal angle of the microphone.

## -remarks

## -see-also

- [ACX_MICROPHONE_TYPE](ne-acxpin-acx_microphone_type.md)
- [acxpin.h header](index.md)

TBD - Please review this topic
