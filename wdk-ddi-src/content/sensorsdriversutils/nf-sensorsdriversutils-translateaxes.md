---
UID: NF:sensorsdriversutils.TranslateAxes
title: TranslateAxes function (sensorsdriversutils.h)
description: The TranslateAxes function applies the rotation matrix to the given sample.
ms.assetid: 5274642e-dbb3-4605-8c29-813d406ed6a3
ms.date: 04/19/2018
keywords: ["TranslateAxes function"]
f1_keywords:
 - "sensorsdriversutils/TranslateAxes"
ms.keywords: TranslateAxes
req.header: sensorsdriversutils.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
topic_type:
- apiref
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- TranslateAxes
product: 
- Windows
targetos: Windows

---

# TranslateAxes function


## -description

The TranslateAxes function applies the rotation matrix to the given sample.

## -parameters

### -param RotationMatrix

Supplies the VEC3D buffer in which the rotation matrix is stored.

### -param RotationMatrixEntryCount

Supplies the number of elements that RotationMatrix holds.

### -param Data

Supplies the VEC3D buffer in which input data is stored and in which the transformed data is returned.

### -param DataCount

Supplies the number of elements that Data holds.

## -remarks

The caller is responsible for saving/restoring the floating point context prior to calling this function.

## -see-also
