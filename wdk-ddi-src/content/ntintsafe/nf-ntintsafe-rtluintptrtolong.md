---
UID: NF:ntintsafe.RtlUIntPtrToLong
title: RtlUIntPtrToLong function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type LONG.
old-location: kernel\rtluintptrtolong.htm
tech.root: kernel
ms.assetid: 03138EBA-F041-47E4-B379-25A96B04E491
ms.date: 04/30/2018
keywords: ["RtlUIntPtrToLong function"]
ms.keywords: RtlUIntPtrToLong, RtlUIntPtrToLong function [Kernel-Mode Driver Architecture], kernel.rtluintptrtolong, ntintsafe/RtlUIntPtrToLong
f1_keywords:
 - "ntintsafe/RtlUIntPtrToLong"
 - "RtlUIntPtrToLong"
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
- RtlUIntPtrToLong
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToLong function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>LONG</b>.


## -parameters




### -param uOperand

<p>The value to be converted.</p>


### -param plResult 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlSizeTToLong
</li>
</ul>


