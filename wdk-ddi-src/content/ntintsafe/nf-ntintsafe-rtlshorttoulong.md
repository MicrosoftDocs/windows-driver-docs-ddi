---
UID: NF:ntintsafe.RtlShortToULong
title: RtlShortToULong function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type ULONG.
old-location: kernel\rtlshorttoulong.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlShortToULong function"]
ms.keywords: RtlShortToULong, RtlShortToULong function [Kernel-Mode Driver Architecture], kernel.rtlshorttoulong, ntintsafe/RtlShortToULong
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
 - RtlShortToULong
 - ntintsafe/RtlShortToULong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlShortToULong
---

# RtlShortToULong function


## -description

Converts a value of type <b>SHORT</b> to a value of type <b>ULONG</b>.

## -parameters

### -param sOperand [in]


The value to be converted.

### -param pulResult [out]


A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlShortToDWord
</li>
<li>RtlInt16ToULong
</li>
<li>RtlInt16ToDWord
</li>
</ul>

