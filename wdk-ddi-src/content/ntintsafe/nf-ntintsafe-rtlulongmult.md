---
UID: NF:ntintsafe.RtlULongMult
title: RtlULongMult function (ntintsafe.h)
description: Multiplies one value of type ULONG by another.
old-location: kernel\rtlulongmult.htm
tech.root: kernel
ms.assetid: 2D5DA884-1746-4DBC-8ABC-2D307181CCAE
ms.date: 04/30/2018
keywords: ["RtlULongMult function"]
ms.keywords: RtlULongMult, RtlULongMult function [Kernel-Mode Driver Architecture], kernel.rtlulongmult, ntintsafe/RtlULongMult
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
 - RtlULongMult
 - ntintsafe/RtlULongMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongMult
---

# RtlULongMult function


## -description

Multiplies one value of type <b>ULONG</b> by another.

## -parameters

### -param ulMultiplicand 

[in]
The value to be multiplied by <i>ulMultiplier</i>.

### -param ulMultiplier 

[in]
The value by which to multiply <i>ulMultiplicand</i>.

### -param pulResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

