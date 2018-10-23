---
UID: NF:sensorsdriversutils.ParseRotationMatrixEntry
title: ParseRotationMatrixEntry function
author: windows-driver-content
description: The ParseRotationMatrixEntry function parses a string of three floats.
ms.assetid: 9f24b18a-f57f-45d4-8372-ea31ae0ead11
ms.date: 04/19/2018
ms.topic: function
ms.keywords: ParseRotationMatrixEntry
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
-	ParseRotationMatrixEntry
product: 
- Windows
targetos: Windows

---

# ParseRotationMatrixEntry function


## -description

The ParseRotationMatrixEntry function parses a string of three floats.

## -parameters

### -param RotationEntry

[in] A string that represents three floats.

### -param Length

[in] Length of the string.

### -param Data

[out] Out buffer for floats.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also
