---
UID: NF:ntintsafe.RtlLongPtrToUChar
title: RtlLongPtrToUChar function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type UCHAR.
old-location: kernel\rtllongptrtouchar.htm
tech.root: kernel
ms.assetid: 86E72C5E-9DB1-4EDD-A6B0-272D4622A500
ms.date: 04/30/2018
ms.keywords: RtlLongPtrToUChar, RtlLongPtrToUChar function [Kernel-Mode Driver Architecture], kernel.rtllongptrtouchar, ntintsafe/RtlLongPtrToUChar
f1_keywords:
 - "ntintsafe/RtlLongPtrToUChar"
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
- RtlLongPtrToUChar
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongPtrToUChar function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>UCHAR</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlSSIZETToUChar
</li>
</ul>


