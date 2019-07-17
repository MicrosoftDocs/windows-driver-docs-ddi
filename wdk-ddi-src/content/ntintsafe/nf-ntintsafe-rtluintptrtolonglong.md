---
UID: NF:ntintsafe.RtlUIntPtrToLongLong
title: RtlUIntPtrToLongLong function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type LONGLONG.
old-location: kernel\rtluintptrtolonglong.htm
tech.root: kernel
ms.assetid: EFEE4662-9FB1-4E44-BE54-2C7932104F28
ms.date: 04/30/2018
ms.keywords: RtlUIntPtrToLongLong, RtlUIntPtrToLongLong function [Kernel-Mode Driver Architecture], kernel.rtluintptrtolonglong, ntintsafe/RtlUIntPtrToLongLong
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlUIntPtrToLongLong"
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
- RtlUIntPtrToLongLong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToLongLong function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>LONGLONG</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pllResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToLong64
</li>
<li>RtlUIntPtrToInt64
</li>
<li>RtlSizeTToLongLong
</li>
<li>RtlSizeTToLong64
</li>
<li>RtlSizeTToInt64
</li>
</ul>


