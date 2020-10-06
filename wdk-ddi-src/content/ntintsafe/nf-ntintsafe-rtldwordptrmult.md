---
UID: NF:ntintsafe.RtlDWordPtrMult
title: RtlDWordPtrMult function (ntintsafe.h)
description: Multiplies one value of type DWORD_PTR by another.
old-location: kernel\rtldwordptrmult.htm
tech.root: kernel
ms.assetid: E7EEE6D7-19C8-481F-BAEF-15998819D2D0
ms.date: 04/30/2018
keywords: ["RtlDWordPtrMult function"]
ms.keywords: RtlDWordPtrMult, RtlDWordPtrMult function [Kernel-Mode Driver Architecture], kernel.rtldwordptrmult, ntintsafe/RtlDWordPtrMult
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlDWordPtrMult
 - ntintsafe/RtlDWordPtrMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlDWordPtrMult
---

# RtlDWordPtrMult function


## -description

Multiplies one value of type <b>DWORD_PTR</b> by another.

## -parameters

### -param dwMultiplicand 

[in]
The value to be multiplied by <i>dwMultiplier</i>.

### -param dwMultiplier 

[in]
The value by which to multiply <i>dwMultiplicand</i>.

### -param pdwResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

