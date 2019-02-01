---
UID: NF:sensorsdriversutils.GetRotationMatrixFromAcpi
title: GetRotationMatrixFromAcpi function (sensorsdriversutils.h)
description: The GetRotationMatrixFromAcpi function reads the rotation matrix from the ACPI entries.
ms.assetid: ac29311e-066a-42ea-9edf-7d114c6b951d
ms.date: 04/19/2018
ms.topic: function
ms.keywords: GetRotationMatrixFromAcpi
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
-	apiref
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	GetRotationMatrixFromAcpi
product: 
- Windows
targetos: Windows

---

# GetRotationMatrixFromAcpi function


## -description

The GetRotationMatrixFromAcpi function reads the rotation matrix from the ACPI entries.

## -parameters

### -param Device

Supplies the WDF device object.

### -param MethodName

Supplies the method name to read.

### -param MethodNameLength

Supplies the method name length in bytes.

### -param RotationMatrix

Supplies the VEC3D buffer in which the rotation matrix is read.

### -param RotationMatrixEntries

Supplies the number of elements that RotationMatrix can hold.

## -returns

This function returns NTSTATUS.

## -remarks

The caller is responsible for saving/restoring the floating point context prior to calling this function.

## -see-also
