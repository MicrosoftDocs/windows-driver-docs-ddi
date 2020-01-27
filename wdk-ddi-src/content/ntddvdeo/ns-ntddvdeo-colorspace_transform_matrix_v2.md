---
UID: NS:ntddvdeo._COLORSPACE_TRANSFORM_MATRIX_V2
title: COLORSPACE_TRANSFORM_MATRIX_V2
author: windows-driver-content
description: The colorspace transform matrix structure.
tech.root: display
ms.assetid: 5f0f66c3-a9d2-4f61-9f40-c0d6bae6657d
ms.author: windowsdriverdev
ms.date: 04/04/2019
f1_keywords:
 - "ntddvdeo/COLORSPACE_TRANSFORM_MATRIX_V2"
ms.keywords: COLORSPACE_TRANSFORM_MATRIX_V2, COLORSPACE_TRANSFORM_MATRIX_V2, *PCOLORSPACE_TRANSFORM_MATRIX_V2, 
req.header: ntddvdeo.h
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
req.typenames: COLORSPACE_TRANSFORM_MATRIX_V2, *PCOLORSPACE_TRANSFORM_MATRIX_V2
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddvdeo.h
api_name: 
 - COLORSPACE_TRANSFORM_MATRIX_V2
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# COLORSPACE_TRANSFORM_MATRIX_V2 structure

## -description

The colorspace transform matrix structure.

## -struct-fields

### -field StageControlLookupTable1DDegamma

The stage control LUT (lookup table) for 1D degamma.

### -field LookupTable1DDegamma

The lookup table 1D degamma.

### -field StageControlColorMatrix3x3

The stage control color matrix.

### -field ColorMatrix3x3

The color matrix.

### -field StageControlLookupTable1DRegamma

The stage control lookup table for 1D regamma.

### -field LookupTable1DRegamma
 
The lookup table 1D regamma.

## -remarks

## -see-also
