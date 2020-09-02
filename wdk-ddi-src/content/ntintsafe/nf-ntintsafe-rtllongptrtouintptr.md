---
UID: NF:ntintsafe.RtlLongPtrToUIntPtr
title: RtlLongPtrToUIntPtr function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type UINT_PTR.
old-location: kernel\rtllongptrtouintptr.htm
tech.root: kernel
ms.assetid: A3AE875A-0794-4EE1-9795-A9CCDC7C8F78
ms.date: 04/30/2018
keywords: ["RtlLongPtrToUIntPtr function"]
ms.keywords: RtlLongPtrToUIntPtr, RtlLongPtrToUIntPtr function [Kernel-Mode Driver Architecture], kernel.rtllongptrtouintptr, ntintsafe/RtlLongPtrToUIntPtr
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
 - RtlLongPtrToUIntPtr
 - ntintsafe/RtlLongPtrToUIntPtr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongPtrToUIntPtr
---

# RtlLongPtrToUIntPtr function


## -description

Converts a value of type <b>LONG_PTR</b> to a value of type <b>UINT_PTR</b>.

## -parameters

### -param lOperand 

[in]
The value to be converted.

### -param puResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongPtrToSizeT
</li>
<li>RtlSSIZETToUIntPtr
</li>
<li>RtlSSIZETToSizeT
</li>
</ul>

