---
UID: NF:ntintsafe.RtlIntPtrToChar
title: RtlIntPtrToChar function (ntintsafe.h)
description: Converts a value of type INT_PTR to a value of type CHAR.
old-location: kernel\rtlintptrtochar.htm
tech.root: kernel
ms.assetid: 96FC52D7-E383-451A-BB30-9C677F254DE2
ms.date: 04/30/2018
keywords: ["RtlIntPtrToChar function"]
ms.keywords: RtlIntPtrToChar, RtlIntPtrToChar function [Kernel-Mode Driver Architecture], kernel.rtlintptrtochar, ntintsafe/RtlIntPtrToChar
f1_keywords:
 - "ntintsafe/RtlIntPtrToChar"
 - "RtlIntPtrToChar"
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
- RtlIntPtrToChar
targetos: Windows
req.typenames: 
---

# RtlIntPtrToChar function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>CHAR</b>.


## -parameters




### -param iOperand 
[in]
The value to be converted.


### -param pch 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlPtrdiffTToChar
</li>
</ul>


