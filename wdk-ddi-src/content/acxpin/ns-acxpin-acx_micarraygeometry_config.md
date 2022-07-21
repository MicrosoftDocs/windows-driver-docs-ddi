---
UID: NS:acxpin._ACX_MICARRAYGEOMETRY_CONFIG
tech.root: audio
title: ACX_MICARRAYGEOMETRY_CONFIG
ms.date: 02/24/2022
targetos: Windows
description: The ACX_MICARRAYGEOMETRY_CONFIG structure is used to configure a microphone array.
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
req.typenames: ACX_MICARRAYGEOMETRY_CONFIG, *PACX_MICARRAYGEOMETRY_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_MICARRAYGEOMETRY_CONFIG
 - PACX_MICARRAYGEOMETRY_CONFIG
 - ACX_MICARRAYGEOMETRY_CONFIG
f1_keywords:
 - _ACX_MICARRAYGEOMETRY_CONFIG
 - acxpin/_ACX_MICARRAYGEOMETRY_CONFIG
 - PACX_MICARRAYGEOMETRY_CONFIG
 - acxpin/PACX_MICARRAYGEOMETRY_CONFIG
 - ACX_MICARRAYGEOMETRY_CONFIG
 - acxpin/ACX_MICARRAYGEOMETRY_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_MICARRAYGEOMETRY_CONFIG** structure is used to configure a microphone array.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_MICARRAYGEOMETRY_CONFIG** structure in bytes.

### -field Flags

A combination of values from the [ACX_MICARRAYGEOMETRY_CONFIG_FLAGS](ne-acxpin-acx_micarraygeometry_config_flags.md) enum that describe the mic array.

### -field Geometry

An [ACX_MIC_ARRAY_GEOMETRY](ns-acxpin-acx_mic_array_geometry.md) structure that specifies the type and the geometry of the microphone array.

## -remarks

The ACX_MICARRAYGEOMETRY_CONFIG structure is used as input to the AcxMicArrayGeometryCreate method.

To initialize an ACX_MICARRAYGEOMETRY_CONFIG structure, your driver should call [ACX_MICARRAYGEOMETRY_CONFIG_INIT](nf-acxpin-acx_micarraygeometry_config_init.md).

## -see-also

- [ACX_MIC_ARRAY_GEOMETRY](ns-acxpin-acx_mic_array_geometry.md)
- [acxpin.h header](index.md)

READY2GO
