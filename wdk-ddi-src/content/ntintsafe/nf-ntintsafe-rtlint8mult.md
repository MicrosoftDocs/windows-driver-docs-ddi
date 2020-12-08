---
UID: NF:ntintsafe.RtlInt8Mult
title: RtlInt8Mult function (ntintsafe.h)
description: Multiplies one value of type INT8 by another.
old-location: kernel\rtlint8mult.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlInt8Mult function"]
ms.keywords: RtlInt8Mult, RtlInt8Mult function [Kernel-Mode Driver Architecture], kernel.rtlint8mult, ntintsafe/RtlInt8Mult
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
 - RtlInt8Mult
 - ntintsafe/RtlInt8Mult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlInt8Mult
---

# RtlInt8Mult function


## -description

Multiplies one value of type <b>INT8</b> by another.

## -parameters

### -param i8Multiplicand 

[in]
The value to be multiplied by <i>i8Multiplier</i>.

### -param i8Multiplier 

[in]
The value by which to multiply <i>i8Multiplicand</i>.

### -param pi8Result 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

