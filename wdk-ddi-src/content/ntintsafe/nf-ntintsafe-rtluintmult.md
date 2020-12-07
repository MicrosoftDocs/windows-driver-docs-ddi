---
UID: NF:ntintsafe.RtlUIntMult
title: RtlUIntMult function (ntintsafe.h)
description: Multiplies one value of type UINT by another.
old-location: kernel\rtluintmult.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlUIntMult function"]
ms.keywords: RtlUIntMult, RtlUIntMult function [Kernel-Mode Driver Architecture], kernel.rtluintmult, ntintsafe/RtlUIntMult
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
 - RtlUIntMult
 - ntintsafe/RtlUIntMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlUIntMult
---

# RtlUIntMult function


## -description

Multiplies one value of type <b>UINT</b> by another.

## -parameters

### -param uMultiplicand 

[in]
The value to be multiplied by <i>uMultiplier</i>.

### -param uMultiplier 

[in]
The value by which to multiply <i>uMultiplicand</i>.

### -param puResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUInt32Mult
</li>
</ul>

