---
UID: NF:ntintsafe.RtlShortToULongPtr
title: RtlShortToULongPtr function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type ULONG_PTR.
old-location: kernel\rtlshorttoulongptr.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlShortToULongPtr function"]
ms.keywords: RtlShortToULongPtr, RtlShortToULongPtr function [Kernel-Mode Driver Architecture], kernel.rtlshorttoulongptr, ntintsafe/RtlShortToULongPtr
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
 - RtlShortToULongPtr
 - ntintsafe/RtlShortToULongPtr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlShortToULongPtr
---

# RtlShortToULongPtr function


## -description

Converts a value of type <b>SHORT</b> to a value of type <b>ULONG_PTR</b>.

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
<li>
RtlLongLongToDWordPtr
</li>
<li>RtlLongLongToSIZET
</li>
<li>RtlLong64ToULongPtr
</li>
<li>RtlLong64ToDWordPtr
</li>
<li>RtlLong64ToSIZET
</li>
<li>RtlInt64ToULongPtr
</li>
<li>RtlInt64ToDWordPtr
</li>
<li>RtlInt64ToSIZET
</li>
<li>RtlShortToSIZET
</li>
<li>RtlInt16ToULongPtr
</li>
<li>RtlInt16ToDWordPtr
</li>
<li>RtlInt16ToSIZET
</li>
</ul>

