---
UID: NF:ntintsafe.RtlIntPtrMult
title: RtlIntPtrMult function (ntintsafe.h)
description: Multiplies one value of type INT_PTR by another.
old-location: kernel\rtlintptrmult.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlIntPtrMult function"]
ms.keywords: RtlIntPtrMult, RtlIntPtrMult function [Kernel-Mode Driver Architecture], kernel.rtlintptrmult, ntintsafe/RtlIntPtrMult
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
 - RtlIntPtrMult
 - ntintsafe/RtlIntPtrMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlIntPtrMult
---

# RtlIntPtrMult function


## -description

Multiplies one value of type <b>INT_PTR</b> by another.

## -parameters

### -param iMultiplicand 

[in]
The value to be multiplied by <i>iMultiplier</i>.

### -param iMultiplier 

[in]
The value by which to multiply <i>iMultiplicand</i>.

### -param piResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

