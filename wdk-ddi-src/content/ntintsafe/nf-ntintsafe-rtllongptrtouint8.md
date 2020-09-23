---
UID: NF:ntintsafe.RtlLongPtrToUInt8
title: RtlLongPtrToUInt8 function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type UINT8.
old-location: kernel\rtllongptrtouint8.htm
tech.root: kernel
ms.assetid: 1E7BB805-1A91-4DA6-A7E9-E60DD8D4AAF3
ms.date: 04/30/2018
keywords: ["RtlLongPtrToUInt8 function"]
ms.keywords: RtlLongPtrToUInt8, RtlLongPtrToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtllongptrtouint8, ntintsafe/RtlLongPtrToUInt8
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
 - RtlLongPtrToUInt8
 - ntintsafe/RtlLongPtrToUInt8
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongPtrToUInt8
---

# RtlLongPtrToUInt8 function


## -description

Converts a value of type <b>LONG_PTR</b> to a value of type <b>UINT8</b>.

## -parameters

### -param lOperand 

[in]
The value to be converted.

### -param pui8Result 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongPtrToByte
</li>
<li>RtlSSIZETToUInt8
</li>
<li>RtlSSIZETToByte
</li>
</ul>

