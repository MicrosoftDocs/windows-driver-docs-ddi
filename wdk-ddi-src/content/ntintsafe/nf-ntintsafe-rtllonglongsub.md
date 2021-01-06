---
UID: NF:ntintsafe.RtlLongLongSub
title: RtlLongLongSub function (ntintsafe.h)
description: Subtracts one value of type LONGLONG from another.
old-location: kernel\rtllonglongsub.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlLongLongSub function"]
ms.keywords: RtlLongLongSub, RtlLongLongSub function [Kernel-Mode Driver Architecture], kernel.rtllonglongsub, ntintsafe/RtlLongLongSub
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
 - RtlLongLongSub
 - ntintsafe/RtlLongLongSub
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongLongSub
---

# RtlLongLongSub function


## -description

Subtracts one value of type <b>LONGLONG</b> from another.

## -parameters

### -param llMinuend 

[in]
The value from which <i>llSubtrahend</i> is subtracted.

### -param llSubtrahend 

[in]
The value to subtract from <i>llMinuend</i>.

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
<li>RtlIntPtrSub
</li>
<li>RtlLongPtrSub
</li>
<li>RtlLong64Sub
</li>
<li>RtlInt64Sub
</li>
<li>RtlPtrdiffTSub
</li>
<li>RtlSSIZETSub
</li>
</ul>

