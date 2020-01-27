---
UID: NF:ntintsafe.RtlUIntPtrToIntPtr
title: RtlUIntPtrToIntPtr function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type INT_PTR.
old-location: kernel\rtluintptrtointptr.htm
tech.root: kernel
ms.assetid: 5340A64A-3A26-4EE1-9829-BFF4F1951FEC
ms.date: 04/30/2018
ms.keywords: RtlUIntPtrToIntPtr, RtlUIntPtrToIntPtr function [Kernel-Mode Driver Architecture], kernel.rtluintptrtointptr, ntintsafe/RtlUIntPtrToIntPtr
f1_keywords:
 - "ntintsafe/RtlUIntPtrToIntPtr"
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
- RtlUIntPtrToIntPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToIntPtr function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>INT_PTR</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToPtrdiffT
</li>
<li>RtlSizeTToIntPtr
</li>
<li>RtlSizeTToPtrdiffT
</li>
</ul>


