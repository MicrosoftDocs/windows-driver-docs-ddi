---
UID: NS:acxpin._ACX_MICARRAYGEOMETRY_CONFIG
tech.root: audio
title: ACX_MICARRAYGEOMETRY_CONFIG
ms.date: 10/05/2021
targetos: Windows
description: 
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

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Flags

Flags from [ACX_MICARRAYGEOMETRY_CONFIG_FLAG](ne-acxpin-acx_micarraygeometry_config_flags.md) to use in creation.

### -field Geometry

An [ACX_MIC_ARRAY_GEOMETRY](ns-acxpin-acx_mic_array_geometry.md) structure that contain the geometry details of the Mic Array.

## -remarks

The ACX_MICARRAYGEOMETRY_CONFIG structure is used as input to the AcxMicArrayGeometryCreate method.

To initialize an ACX_MICARRAYGEOMETRY_CONFIG structure, your driver should call [ACX_MICARRAYGEOMETRY_CONFIG_INIT](nf-acxpin-acx_micarraygeometry_config_init.md).

## -see-also

READY2GO
