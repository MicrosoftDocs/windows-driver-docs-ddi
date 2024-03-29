---
UID: NF:ntintsafe.RtlIntPtrToULongLong
title: RtlIntPtrToULongLong function (ntintsafe.h)
description: Converts a value of type INT_PTR to a value of type ULONGLONG.
old-location: kernel\rtlintptrtoulonglong.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlIntPtrToULongLong function"]
ms.keywords: RtlIntPtrToULongLong, RtlIntPtrToULongLong function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoulonglong, ntintsafe/RtlIntPtrToULongLong
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
 - RtlIntPtrToULongLong
 - ntintsafe/RtlIntPtrToULongLong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlIntPtrToULongLong
---

# RtlIntPtrToULongLong function


## -description

Converts a value of type <b>INT_PTR</b> to a value of type <b>ULONGLONG</b>.

## -parameters

### -param iOperand [in]


The value to be converted.

### -param pullResult [out]


A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToDWordLong
</li>
<li>RtlIntPtrToULong64
</li>
<li>RtlIntPtrToDWord64
</li>
<li>RtlIntPtrToUInt64
</li>
<li>RtlPtrdiffTToULongLong
</li>
<li>RtlPtrdiffTToDWordLong
</li>
<li>RtlPtrdiffTToULong64
</li>
<li>RtlPtrdiffTToDWord64
</li>
<li>RtlPtrdiffTToUInt64
</li>
</ul>

