---
UID: NS:ntddvdeo._COLORSPACE_TRANSFORM_DATA_CAP
title: COLORSPACE_TRANSFORM_DATA_CAP
author: windows-driver-content
description: The colorspace transform data cap.
tech.root: display
ms.assetid: d884b2ba-c7de-4165-82b6-bd0999d7ab8a
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["COLORSPACE_TRANSFORM_DATA_CAP structure"]
ms.keywords: COLORSPACE_TRANSFORM_DATA_CAP, COLORSPACE_TRANSFORM_DATA_CAP,
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
req.typenames: COLORSPACE_TRANSFORM_DATA_CAP
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _COLORSPACE_TRANSFORM_DATA_CAP
 - ntddvdeo/_COLORSPACE_TRANSFORM_DATA_CAP
 - COLORSPACE_TRANSFORM_DATA_CAP
 - ntddvdeo/COLORSPACE_TRANSFORM_DATA_CAP
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - COLORSPACE_TRANSFORM_DATA_CAP
dev_langs:
 - c++
---

# COLORSPACE_TRANSFORM_DATA_CAP structure


## -description

The colorspace transform data cap.

## -struct-fields

### -field DataType

A [COLORSPACE_TRANSFORM_DATA_TYPE](ne-ntddvdeo-colorspace_transform_data_type.md) enumeration.

### -field BitCountOfInteger

Bit count of integer if *DataType* is fixed-point(COLORSPACE_TRANSFORM_DATA_TYPE_FIXED_POINT).

### -field BitCountOfFraction

Bit count of fraction if *DataType* is fixed-point(COLORSPACE_TRANSFORM_DATA_TYPE_FIXED_POINT).

### -field BitCountOfExponent

Bit count of exponent if the *DataType* is float(COLORSPACE_TRANSFORM_DATA_TYPE_FLOAT).

### -field BitCountOfMantissa

Bit count of mantissa if the DataType is float(COLORSPACE_TRANSFORM_DATA_TYPE_FLOAT).

### -field Value

### -field NumericRangeMin

Minimum number of gamma data.

### -field NumericRangeMax

 
Maximum number of gamma data.

## -remarks

## -see-also

