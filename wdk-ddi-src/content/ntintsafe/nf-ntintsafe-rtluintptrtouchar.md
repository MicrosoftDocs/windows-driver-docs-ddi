---
UID: NF:ntintsafe.RtlUIntPtrToUChar
title: RtlUIntPtrToUChar function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type UCHAR.
old-location: kernel\rtluintptrtouchar.htm
tech.root: kernel
ms.assetid: F5E4225F-4C66-44A8-9445-7D7DBAFA1DA4
ms.date: 04/30/2018
keywords: ["RtlUIntPtrToUChar function"]
ms.keywords: RtlUIntPtrToUChar, RtlUIntPtrToUChar function [Kernel-Mode Driver Architecture], kernel.rtluintptrtouchar, ntintsafe/RtlUIntPtrToUChar
f1_keywords:
 - "ntintsafe/RtlUIntPtrToUChar"
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
- RtlUIntPtrToUChar
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToUChar function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>UCHAR</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlSizeTToUChar
</li>
</ul>


