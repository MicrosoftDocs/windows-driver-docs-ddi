---
UID: NF:ntintsafe.RtlDWordPtrAdd
title: RtlDWordPtrAdd function (ntintsafe.h)
description: Adds two values of type DWORD_PTR.
old-location: kernel\rtldwordptradd.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlDWordPtrAdd function"]
ms.keywords: RtlDWordPtrAdd, RtlDWordPtrAdd function [Kernel-Mode Driver Architecture], kernel.rtldwordptradd, ntintsafe/RtlDWordPtrAdd
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
 - RtlDWordPtrAdd
 - ntintsafe/RtlDWordPtrAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlDWordPtrAdd
---

# RtlDWordPtrAdd function


## -description

Adds two values of type <b>DWORD_PTR</b>.

## -parameters

### -param dwAugend [in]


The first value in the equation.

### -param dwAddend [in]


The value to add to <i>dwAugend</i>.

### -param pdwResult [out]


A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

