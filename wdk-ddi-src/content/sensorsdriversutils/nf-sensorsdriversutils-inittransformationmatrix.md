---
UID: NF:sensorsdriversutils.InitTransformationMatrix
title: InitTransformationMatrix function (sensorsdriversutils.h)
description: The InitTransformationMatrix function reads the rotation matrix from the ACPI entries.
tech.root: sensors
ms.date: 04/19/2018
keywords: ["InitTransformationMatrix function"]
ms.keywords: InitTransformationMatrix
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
targetos: Windows
f1_keywords:
 - InitTransformationMatrix
 - sensorsdriversutils/InitTransformationMatrix
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - InitTransformationMatrix
product:
 - Windows
---

# InitTransformationMatrix function


## -description

The InitTransformationMatrix function reads the rotation matrix from the ACPI entries.

## -parameters

### -param Device

Supplies the WDF device object.

### -param RotationMatrix

Supplies the VEC3D buffer in which the rotation matrix is read.

### -param RotationMatrixEntryCount

Supplies the number of elements that RotationMatrix can hold.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

