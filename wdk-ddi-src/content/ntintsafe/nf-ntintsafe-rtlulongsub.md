---
UID: NF:ntintsafe.RtlULongSub
title: RtlULongSub function (ntintsafe.h)
description: Subtracts one value of type ULONG from another.
old-location: kernel\rtlulongsub.htm
tech.root: kernel
ms.assetid: 54776F17-C7EE-46DB-BA3F-2F545240FC61
ms.date: 04/30/2018
keywords: ["RtlULongSub function"]
ms.keywords: RtlULongSub, RtlULongSub function [Kernel-Mode Driver Architecture], kernel.rtlulongsub, ntintsafe/RtlULongSub
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
 - RtlULongSub
 - ntintsafe/RtlULongSub
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongSub
---

# RtlULongSub function


## -description

Subtracts one value of type <b>ULONG</b> from another.

## -parameters

### -param ulMinuend 

[in]
The value from which <i>ulSubtrahend</i> is subtracted.

### -param ulSubtrahend 

[in]
The value to subtract from <i>ulMinuend</i>.

### -param pulResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

