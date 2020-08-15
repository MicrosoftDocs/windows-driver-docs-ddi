---
UID: NF:ntintsafe.RtlIntPtrToLongPtr
title: RtlIntPtrToLongPtr function (ntintsafe.h)
description: Converts a value of type INT_PTR to a value of type LONG_PTR.
old-location: kernel\rtlintptrtolongptr.htm
tech.root: kernel
ms.assetid: B04AE198-6677-4975-BAA0-96C228EFB038
ms.date: 04/30/2018
keywords: ["RtlIntPtrToLongPtr function"]
ms.keywords: RtlIntPtrToLongPtr, RtlIntPtrToLongPtr function [Kernel-Mode Driver Architecture], kernel.rtlintptrtolongptr, ntintsafe/RtlIntPtrToLongPtr
f1_keywords:
 - "ntintsafe/RtlIntPtrToLongPtr"
 - "RtlIntPtrToLongPtr"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntintsafe.h
api_name:
- RtlIntPtrToLongPtr
targetos: Windows
req.typenames: 
---

# RtlIntPtrToLongPtr function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>LONG_PTR</b>.


## -parameters




### -param iOperand 
[in]
The value to be converted.


### -param plResult 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlPtrdiffTToLongPtr
</li>
</ul>


