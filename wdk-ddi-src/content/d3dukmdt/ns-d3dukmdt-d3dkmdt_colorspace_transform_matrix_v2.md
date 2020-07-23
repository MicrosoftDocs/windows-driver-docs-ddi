---
UID: NS:d3dukmdt._D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2
title: D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2
author: windows-driver-content
description: Structure to describe the 3 by 4 matrix color space transform.
tech.root: display
ms.assetid: 66c5b473-3479-4c68-88ba-cc1974e9af48
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2 structure"]
f1_keywords:
 - "d3dukmdt/D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2"
 - "D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2"
ms.keywords: D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2, D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2, *PD3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2, 
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2, *PD3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dukmdt.h
api_name: 
 - D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2 structure

## -description

Structure to describe the 3 by 4 matrix color space transform.

## -struct-fields

### -field StageControlLookupTable1DDegamma

Stage control of lookup table 1D degamma.

### -field LookupTable1DDegamma

The lookup table 1D degamma.

### -field StageControlColorMatrix3x3

Stage control of a 3x3 matrix.

### -field ColorMatrix3x3

The color 3x3 matrix.

### -field StageControlLookupTable1DRegamma

Stage control of lookup table 1D regamma.

### -field LookupTable1DRegamma
 
The lookup table 1D regamma.

## -remarks

## -see-also
