---
UID: NF:ntintsafe.RtlUIntPtrAdd
title: RtlUIntPtrAdd function (ntintsafe.h)
description: Adds two values of type UINT_PTR.
old-location: kernel\rtluintptradd.htm
tech.root: kernel
ms.assetid: 9106CE96-A26F-4358-9668-2C0E331BB793
ms.date: 04/30/2018
keywords: ["RtlUIntPtrAdd function"]
ms.keywords: RtlUIntPtrAdd, RtlUIntPtrAdd function [Kernel-Mode Driver Architecture], kernel.rtluintptradd, ntintsafe/RtlUIntPtrAdd
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
 - RtlUIntPtrAdd
 - ntintsafe/RtlUIntPtrAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlUIntPtrAdd
---

# RtlUIntPtrAdd function


## -description

Adds two values of type <b>UINT_PTR</b>.

## -parameters

### -param uAugend 

[in]
The first value in the equation.

### -param uAddend 

[in]
The value to add to <i>uAugend</i>.

### -param puResult 

[out]
A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlDWordAdd
</li>
<li>RtlUIntPtrAdd
</li>
<li>RtlULongPtrAdd
</li>
<li>RtlDWordPtrAdd
</li>
<li>RtlSIZETAdd
</li>
<li>RtlDWordLongAdd
</li>
<li>RtlULong64Add
</li>
<li>RtlDWord64Add
</li>
<li>RtlUInt64Add
</li>
</ul>

