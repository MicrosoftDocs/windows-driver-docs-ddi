---
UID: NF:ntintsafe.RtlULongPtrToInt8
title: RtlULongPtrToInt8 function (ntintsafe.h)
description: Converts a value of type ULONG_PTR to a value of type INT8.
old-location: kernel\rtlulongptrtoint8.htm
tech.root: kernel
ms.assetid: D2A77B0A-9307-4090-AE3D-049E5C414D31
ms.date: 04/30/2018
ms.keywords: RtlULongPtrToInt8, RtlULongPtrToInt8 function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtoint8, ntintsafe/RtlULongPtrToInt8
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlULongPtrToInt8"
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
- RtlULongPtrToInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongPtrToInt8 function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>INT8</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



