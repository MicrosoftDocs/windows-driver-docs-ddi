---
UID: NF:ntintsafe.RtlLongPtrToShort
title: RtlLongPtrToShort function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type SHORT.
old-location: kernel\rtllongptrtoshort.htm
tech.root: kernel
ms.assetid: 934967A0-9CEF-4377-9505-EE4C4E9AF706
ms.date: 04/30/2018
keywords: ["RtlLongPtrToShort function"]
ms.keywords: RtlLongPtrToShort, RtlLongPtrToShort function [Kernel-Mode Driver Architecture], kernel.rtllongptrtoshort, ntintsafe/RtlLongPtrToShort
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
 - RtlLongPtrToShort
 - ntintsafe/RtlLongPtrToShort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongPtrToShort
---

# RtlLongPtrToShort function


## -description

Converts a value of type <b>LONG_PTR</b> to a value of type <b>SHORT</b>.

## -parameters

### -param lOperand 

[in]
The value to be converted.

### -param psResult 

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
RtlLongPtrToInt16
</li>
<li>RtlSSIZETToShort
</li>
<li>RtlSSIZETToInt16
</li>
</ul>

