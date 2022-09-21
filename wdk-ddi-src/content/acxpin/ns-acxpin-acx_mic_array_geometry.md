---
UID: NS:acxpin._ACX_MIC_ARRAY_GEOMETRY
tech.root: audio
title: ACX_MIC_ARRAY_GEOMETRY
ms.date: 07/22/2022
targetos: Windows
description: The ACX_MIC_ARRAY_GEOMETRY structure specifies the type and the geometry of the microphone array.
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
req.typenames: ACX_MIC_ARRAY_GEOMETRY, *PACX_MIC_ARRAY_GEOMETRY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_MIC_ARRAY_GEOMETRY
 - PACX_MIC_ARRAY_GEOMETRY
 - ACX_MIC_ARRAY_GEOMETRY
f1_keywords:
 - _ACX_MIC_ARRAY_GEOMETRY
 - acxpin/_ACX_MIC_ARRAY_GEOMETRY
 - PACX_MIC_ARRAY_GEOMETRY
 - acxpin/PACX_MIC_ARRAY_GEOMETRY
 - ACX_MIC_ARRAY_GEOMETRY
 - acxpin/ACX_MIC_ARRAY_GEOMETRY
dev_langs:
 - c++
---

## -description

The **ACX_MIC_ARRAY_GEOMETRY** structure specifies the type and the geometry of the microphone array.

## -struct-fields

### -field Version

Specifies the version number of the mic array specification. It is currently set to 0x0100, which represents a version number of 1.0.

### -field MicArrayType

Specifies the type of microphone array in use. This member can be any one of the [ACX_MIC_ARRAY_TYPE](ne-acxpin-acx_mic_array_type.md) enumeration values.

### -field VerticalAngleBegin

Specifies the vertical angle of the start of the working volume of the microphone array.

### -field VerticalAngleEnd

Specifies the vertical angle of the end of the working volume of the microphone array.

### -field HorizontalAngleBegin

Specifies the work volume horizontal angle begin.

### -field HorizontalAngleEnd

Specifies the work volume horizontal angle end.

### -field FrequencyBandLo

Specifies the low end of the frequency range for the microphone array.

### -field FrequencyBandHi

Specifies the high end of the frequency range for the microphone array.

## -remarks

All angle values are expressed in units of 1/10000th of a radian. For example, 3.1416 radians is expressed as 31416 units. Acceptable values range from -31416 to 31416 units.

All coordinate values are expressed in millimeters. Acceptable values range from -32768 to 32767, inclusive.

Frequency values are expressed in Hertz (Hz).

For more information about how to process a microphone array in Windows, see the [Microphone array support in Windows](/previous-versions/windows/hardware/design/dn613960(v=vs.85)) white paper.

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_MIC_ARRAY_TYPE](ne-acxpin-acx_mic_array_type.md)
- [Microphone array support in Windows](/previous-versions/windows/hardware/design/dn613960(v=vs.85))
- [acxpin.h header](index.md)


