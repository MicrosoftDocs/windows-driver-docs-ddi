---
UID: NF:ntintsafe.RtlULongPtrToChar
title: RtlULongPtrToChar function (ntintsafe.h)
description: Converts a value of type ULONG_PTR to a value of type CHAR.
old-location: kernel\rtlulongptrtochar.htm
tech.root: kernel
ms.assetid: DB015FC3-D263-4EA6-AAE1-E4ECA3ECF4F9
ms.date: 04/30/2018
keywords: ["RtlULongPtrToChar function"]
ms.keywords: RtlULongPtrToChar, RtlULongPtrToChar function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtochar, ntintsafe/RtlULongPtrToChar
f1_keywords:
 - "ntintsafe/RtlULongPtrToChar"
 - "RtlULongPtrToChar"
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
- RtlULongPtrToChar
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongPtrToChar function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>CHAR</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



