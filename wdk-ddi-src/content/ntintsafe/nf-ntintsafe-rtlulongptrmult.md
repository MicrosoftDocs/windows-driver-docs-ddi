---
UID: NF:ntintsafe.RtlULongPtrMult
title: RtlULongPtrMult function (ntintsafe.h)
description: Multiplies one value of type ULONG_PTR by another.
old-location: kernel\rtlulongptrmult.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlULongPtrMult function"]
ms.keywords: RtlULongPtrMult, RtlULongPtrMult function [Kernel-Mode Driver Architecture], kernel.rtlulongptrmult, ntintsafe/RtlULongPtrMult
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
 - RtlULongPtrMult
 - ntintsafe/RtlULongPtrMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongPtrMult
---

# RtlULongPtrMult function


## -description

Multiplies one value of type <b>ULONG_PTR</b> by another.

## -parameters

### -param ulMultiplicand

<p>The value to be multiplied by <i>Multiplier</i>.</p>

### -param ulMultiplier

<p>The value by which to multiply <i>Multiplicand</i>.</p>

### -param pulResult

<p>A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

