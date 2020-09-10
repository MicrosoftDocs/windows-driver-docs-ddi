---
UID: NF:ntintsafe.RtlLongPtrToULongLong
title: RtlLongPtrToULongLong function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type ULONGLONG.
old-location: kernel\rtllongptrtoulonglong.htm
tech.root: kernel
ms.assetid: E0CAA44B-2432-4199-B2E6-8105FD7BA504
ms.date: 04/30/2018
keywords: ["RtlLongPtrToULongLong function"]
ms.keywords: RtlLongPtrToULongLong, RtlLongPtrToULongLong function [Kernel-Mode Driver Architecture], kernel.rtllongptrtoulonglong, ntintsafe/RtlLongPtrToULongLong
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
 - RtlLongPtrToULongLong
 - ntintsafe/RtlLongPtrToULongLong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongPtrToULongLong
---

# RtlLongPtrToULongLong function


## -description

Converts a value of type <b>LONG_PTR</b> to a value of type <b>ULONGLONG</b>.

## -parameters

### -param lOperand 

[in]
The value to be converted.

### -param pullResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongPtrToDWordLong
</li>
<li>RtlLongPtrToULong64
</li>
<li>RtlLongPtrToDWord64
</li>
<li>RtlLongPtrToUInt64
</li>
<li>RtlSSIZETToULongLong
</li>
<li>RtlSSIZETToDWordLong
</li>
<li>RtlSSIZETToULong64
</li>
<li>RtlSSIZETToDWord64
</li>
<li>RtlSSIZETToUInt64
</li>
</ul>

