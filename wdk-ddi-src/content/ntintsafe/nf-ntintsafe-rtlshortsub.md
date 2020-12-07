---
UID: NF:ntintsafe.RtlShortSub
title: RtlShortSub function (ntintsafe.h)
description: Subtracts one value of type SHORT from another.
old-location: kernel\rtlshortsub.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlShortSub function"]
ms.keywords: RtlShortSub, RtlShortSub function [Kernel-Mode Driver Architecture], kernel.rtlshortsub, ntintsafe/RtlShortSub
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
 - RtlShortSub
 - ntintsafe/RtlShortSub
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlShortSub
---

# RtlShortSub function


## -description

Subtracts one value of type <b>SHORT</b> from another.

## -parameters

### -param sMinuend 

[in]
The value from which <i>sSubtrahend</i> is subtracted.

### -param sSubtrahend 

[in]
The value to subtract from <i>sMinuend</i>.

### -param psResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt16Sub
</li>
</ul>

