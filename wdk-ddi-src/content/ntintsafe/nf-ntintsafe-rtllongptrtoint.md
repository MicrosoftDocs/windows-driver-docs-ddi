---
UID: NF:ntintsafe.RtlLongPtrToInt
title: RtlLongPtrToInt function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type INT.
old-location: kernel\rtllongptrtoint.htm
tech.root: kernel
ms.assetid: 265CABEE-E2FD-4ACA-9C82-54291E63479B
ms.date: 04/30/2018
keywords: ["RtlLongPtrToInt function"]
ms.keywords: RtlLongPtrToInt, RtlLongPtrToInt function [Kernel-Mode Driver Architecture], kernel.rtllongptrtoint, ntintsafe/RtlLongPtrToInt
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
 - RtlLongPtrToInt
 - ntintsafe/RtlLongPtrToInt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongPtrToInt
---

# RtlLongPtrToInt function


## -description

Converts a value of type <b>LONG_PTR</b> to a value of type <b>INT</b>.

## -parameters

### -param lOperand 

[in]
The value to be converted.

### -param piResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongPtrToInt32
</li>
<li>RtlSSIZETToInt
</li>
<li>RtlSSIZETToInt32
</li>
</ul>

