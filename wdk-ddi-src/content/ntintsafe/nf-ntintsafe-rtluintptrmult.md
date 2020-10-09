---
UID: NF:ntintsafe.RtlUIntPtrMult
title: RtlUIntPtrMult function (ntintsafe.h)
description: Multiplies one value of type UINT_PTR by another.
old-location: kernel\rtluintptrmult.htm
tech.root: kernel
ms.assetid: E484AB83-DEA6-4FC7-9896-26984D998661
ms.date: 04/30/2018
keywords: ["RtlUIntPtrMult function"]
ms.keywords: RtlUIntPtrMult, RtlUIntPtrMult function [Kernel-Mode Driver Architecture], kernel.rtluintptrmult, ntintsafe/RtlUIntPtrMult
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
 - RtlUIntPtrMult
 - ntintsafe/RtlUIntPtrMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlUIntPtrMult
---

# RtlUIntPtrMult function


## -description

Multiplies one value of type <b>UINT_PTR</b> by another.

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
<li>RtlUIntPtrMult
</li>
<li>RtlULongPtrMult
</li>
<li>RtlDWordPtrMult
</li>
<li>RtlSizeTMult
</li>
<li>RtlSIZETMult
</li>
<li>RtlDWordLongMult
</li>
<li>RtlULong64Mult
</li>
<li>RtlDWord64Mult
</li>
<li>RtlUInt64Mult
</li>
</ul>

