---
UID: NF:ntintsafe.RtlSizeTSub
title: RtlSizeTSub function (ntintsafe.h)
description: Subtracts one value of type SIZE_T from another.
old-location: kernel\rtlsizetsub.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlSizeTSub function"]
ms.keywords: RtlSizeTSub, RtlSizeTSub function [Kernel-Mode Driver Architecture], kernel.rtlsizetsub, ntintsafe/RtlSizeTSub
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
 - RtlSizeTSub
 - ntintsafe/RtlSizeTSub
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlSizeTSub
---

# RtlSizeTSub function


## -description

Subtracts one value of type <b>SIZE_T</b> from another.

## -parameters

### -param Minuend 

[in]
The value from which <i>Subtrahend</i> is subtracted.

### -param Subtrahend 

[in]
The value to subtract from <i>Minuend</i>.

### -param pResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

