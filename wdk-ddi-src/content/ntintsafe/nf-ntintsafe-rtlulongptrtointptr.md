---
UID: NF:ntintsafe.RtlULongPtrToIntPtr
title: RtlULongPtrToIntPtr function (ntintsafe.h)
description: Converts a value of type ULONG_PTR to a value of type INT_PTR.
old-location: kernel\rtlulongptrtointptr.htm
tech.root: kernel
ms.assetid: 41687454-5468-4351-BEAF-2FB6BD80BEFC
ms.date: 04/30/2018
ms.keywords: RtlULongPtrToIntPtr, RtlULongPtrToIntPtr function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtointptr, ntintsafe/RtlULongPtrToIntPtr
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlULongPtrToIntPtr"
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
- RtlULongPtrToIntPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongPtrToIntPtr function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>INT_PTR</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



