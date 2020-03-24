---
UID: NF:ntintsafe.RtlUIntPtrToUShort
title: RtlUIntPtrToUShort function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type USHORT.
old-location: kernel\rtluintptrtoushort.htm
tech.root: kernel
ms.assetid: 7C65771B-B60E-459F-AB71-1091B45C5A1A
ms.date: 04/30/2018
keywords: ["RtlUIntPtrToUShort function"]
ms.keywords: RtlUIntPtrToUShort, RtlUIntPtrToUShort function [Kernel-Mode Driver Architecture], kernel.rtluintptrtoushort, ntintsafe/RtlUIntPtrToUShort
f1_keywords:
 - "ntintsafe/RtlUIntPtrToUShort"
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
- RtlUIntPtrToUShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToUShort function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>USHORT</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToWord
</li>
<li>RtlSizeTToUShort
</li>
<li>RtlSizeTToUInt16
</li>
<li>RtlSizeTToWord
</li>
</ul>


