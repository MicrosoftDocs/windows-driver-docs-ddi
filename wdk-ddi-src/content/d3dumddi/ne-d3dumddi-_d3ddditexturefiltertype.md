---
UID: NE:d3dumddi._D3DDDITEXTUREFILTERTYPE
title: _D3DDDITEXTUREFILTERTYPE (d3dumddi.h)
description: The texture filter type.
ms.assetid: 4219ecb5-c052-4952-b955-4b8f3653744b
ms.date: 10/19/2018
keywords: ["_D3DDDITEXTUREFILTERTYPE enumeration"]
ms.keywords: _D3DDDITEXTUREFILTERTYPE, D3DDDITEXTUREFILTERTYPE,
req.header: d3dumddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DDDITEXTUREFILTERTYPE
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - "d3dumddi/_D3DDDITEXTUREFILTERTYPE"
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDITEXTUREFILTERTYPE
product:
 - Windows
dev_langs:
 - c++
---

# _D3DDDITEXTUREFILTERTYPE enumeration

## -description

The texture filter type.

## -enum-fields

### -field D3DDDITEXF_NONE

Filtering disabled.

### -field D3DDDITEXF_POINT

Nearest.

### -field D3DDDITEXF_LINEAR

Linear interpolation.

### -field D3DDDITEXF_ANISOTROPIC

Anisotropic.

### -field D3DDDITEXF_PYRAMIDALQUAD

4-sample tent.

### -field D3DDDITEXF_GAUSSIANQUAD

4-sample gaussian.

### -field D3DDDITEXF_FORCE_UINT

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.

## -remarks

## -see-also

