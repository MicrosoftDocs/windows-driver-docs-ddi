---
UID: NS:d3dkmddi._DKGK_GAMMA_DATA_CAP
title: DKGK_GAMMA_DATA_CAP
author: windows-driver-content
description: Gamma data caps.
tech.root: display
ms.assetid: ff38c435-e1d4-48a9-8762-803e1619f6f1
ms.author: windowsdriverdev
ms.date: 04/04/2019
f1_keywords:
 - "d3dkmddi/DKGK_GAMMA_DATA_CAP"
ms.keywords: DKGK_GAMMA_DATA_CAP, DKGK_GAMMA_DATA_CAP, 
req.header: d3dkmddi.h
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
req.typenames: DKGK_GAMMA_DATA_CAP
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmddi.h
api_name: 
 - DKGK_GAMMA_DATA_CAP
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DKGK_GAMMA_DATA_CAP structure

## -description

Gamma data caps.

## -struct-fields

### -field DataType

A [DXGK_GAMMA_DATA_TYPE](ne-d3dkmddi-dxgk_gamma_data_type.md) enumeration value.

### -field BitCountOfInteger

Bit count of integer if *DataType* is fixed-point(**DXGK_GAMMA_DATA_TYPE_FIXED_POINT**).

### -field BitCountOfFraction

Bit count of fraction if *DataType* is fixed-point(**DXGK_GAMMA_DATA_TYPE_FIXED_POINT**).

### -field BitCountOfExponent

Bit count of exponent if the *DataType* is float(**DXGK_GAMMA_DATA_TYPE_FLOAT**).

### -field BitCountOfMantissa

Bit count of mantissa if the *DataType* is float(**DXGK_GAMMA_DATA_TYPE_FLOAT**).

### -field Value
 
### -field NumericRangeMin

Minimum number of gamma data.

### -field NumericRangeMax
 
Maximum number of gamma data.

## -remarks

## -see-also
