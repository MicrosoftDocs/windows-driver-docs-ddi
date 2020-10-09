---
UID: NF:ntintsafe.RtlLongPtrSub
title: RtlLongPtrSub function (ntintsafe.h)
description: Subtracts one value of type LONG_PTR from another.
old-location: kernel\rtllongptrsub.htm
tech.root: kernel
ms.assetid: 3F95CA04-3CE1-4298-B3B6-5D111AB4F3D3
ms.date: 04/30/2018
keywords: ["RtlLongPtrSub function"]
ms.keywords: RtlLongPtrSub, RtlLongPtrSub function [Kernel-Mode Driver Architecture], kernel.rtllongptrsub, ntintsafe/RtlLongPtrSub
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
 - RtlLongPtrSub
 - ntintsafe/RtlLongPtrSub
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongPtrSub
---

# RtlLongPtrSub function


## -description

Subtracts one value of type <b>LONG_PTR</b> from another.

## -parameters

### -param lMinuend 

[in]
The value from which <i>lSubtrahend</i> is subtracted.

### -param lSubtrahend 

[in]
The value to subtract from <i>lMinuend</i>.

### -param plResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

