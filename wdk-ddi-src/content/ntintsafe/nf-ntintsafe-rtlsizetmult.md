---
UID: NF:ntintsafe.RtlSizeTMult
title: RtlSizeTMult function (ntintsafe.h)
description: Multiplies one value of type SIZE_T by another.
old-location: kernel\rtlsizetmult.htm
tech.root: kernel
ms.assetid: 3EC72857-2880-4F03-8CC3-9B9A80F19273
ms.date: 04/30/2018
keywords: ["RtlSizeTMult function"]
ms.keywords: RtlSizeTMult, RtlSizeTMult function [Kernel-Mode Driver Architecture], kernel.rtlsizetmult, ntintsafe/RtlSizeTMult
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
 - RtlSizeTMult
 - ntintsafe/RtlSizeTMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlSizeTMult
---

# RtlSizeTMult function


## -description

Multiplies one value of type <b>SIZE_T</b> by another.

## -parameters

### -param Multiplicand 

[in]
The value to be multiplied by <i>Multiplier</i>.

### -param Multiplier 

[in]
The value by which to multiply <i>Multiplicand</i>.

### -param pResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

