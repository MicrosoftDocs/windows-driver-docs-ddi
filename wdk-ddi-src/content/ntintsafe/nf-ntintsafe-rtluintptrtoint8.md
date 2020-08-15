---
UID: NF:ntintsafe.RtlUIntPtrToInt8
title: RtlUIntPtrToInt8 function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type INT8.
old-location: kernel\rtluintptrtoint8.htm
tech.root: kernel
ms.assetid: BA484BB1-550E-48F1-A400-86F62D59A0A1
ms.date: 04/30/2018
keywords: ["RtlUIntPtrToInt8 function"]
ms.keywords: RtlUIntPtrToInt8, RtlUIntPtrToInt8 function [Kernel-Mode Driver Architecture], kernel.rtluintptrtoint8, ntintsafe/RtlUIntPtrToInt8
f1_keywords:
 - "ntintsafe/RtlUIntPtrToInt8"
 - "RtlUIntPtrToInt8"
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
- RtlUIntPtrToInt8
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToInt8 function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>INT8</b>.


## -parameters




### -param uOperand 
[in]
The value to be converted.


### -param pi8Result 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlSizeTToInt8
</li>
</ul>


