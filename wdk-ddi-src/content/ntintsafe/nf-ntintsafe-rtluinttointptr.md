---
UID: NF:ntintsafe.RtlUIntToIntPtr
title: RtlUIntToIntPtr function (ntintsafe.h)
description: Converts a value of type UINT to a value of type INT_PTR.
old-location: kernel\rtluinttointptr.htm
tech.root: kernel
ms.assetid: CCFC8531-4BFB-4CFA-8B57-A4FFD4151900
ms.date: 04/30/2018
ms.keywords: RtlUIntToIntPtr, RtlUIntToIntPtr function [Kernel-Mode Driver Architecture], kernel.rtluinttointptr, ntintsafe/RtlUIntToIntPtr
f1_keywords:
 - "ntintsafe/RtlUIntToIntPtr"
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
- RtlUIntToIntPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntToIntPtr function


## -description


Converts a value of type <b>UINT</b> to a value of type <b>INT_PTR</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



