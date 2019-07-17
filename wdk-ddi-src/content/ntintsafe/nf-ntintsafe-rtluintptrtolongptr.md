---
UID: NF:ntintsafe.RtlUIntPtrToLongPtr
title: RtlUIntPtrToLongPtr function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type LONG_PTR.
old-location: kernel\rtluintptrtolongptr.htm
tech.root: kernel
ms.assetid: FF032898-E1BB-4821-A685-3774B1DBFADA
ms.date: 04/30/2018
ms.keywords: RtlUIntPtrToLongPtr, RtlUIntPtrToLongPtr function [Kernel-Mode Driver Architecture], kernel.rtluintptrtolongptr, ntintsafe/RtlUIntPtrToLongPtr
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlUIntPtrToLongPtr"
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
- RtlUIntPtrToLongPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToLongPtr function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>LONG_PTR</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToSSIZET
</li>
<li>RtlSizeTToLongPtr
</li>
<li>RtlSizeTToSSIZET
</li>
</ul>


