---
UID: NF:ntintsafe.RtlLongLongMult
title: RtlLongLongMult function (ntintsafe.h)
description: Multiplies one value of type LONGLONG by another.
old-location: kernel\rtllonglongmult.htm
tech.root: kernel
ms.assetid: E5FE5EDB-D11D-4EF7-9CEA-CF059398A063
ms.date: 04/30/2018
keywords: ["RtlLongLongMult function"]
ms.keywords: RtlLongLongMult, RtlLongLongMult function [Kernel-Mode Driver Architecture], kernel.rtllonglongmult, ntintsafe/RtlLongLongMult
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
 - RtlLongLongMult
 - ntintsafe/RtlLongLongMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongLongMult
---

# RtlLongLongMult function


## -description

Multiplies one value of type <b>LONGLONG</b> by another.

## -parameters

### -param llMultiplicand 

[in]
The value to be multiplied by <i>llMultiplier</i>.

### -param llMultiplier 

[in]
The value by which to multiply <i>llMultiplicand</i>.

### -param pllResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrMult
</li>
<li>RtlLongPtrMult
</li>
<li>RtlLong64Mult
</li>
<li>RtlInt64Mult
</li>
<li>RtlPtrdiffTMult
</li>
<li>RtlSSIZETMult
</li>
</ul>

