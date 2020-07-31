---
UID: NF:ntintsafe.RtlInt8ToULongPtr
title: RtlInt8ToULongPtr function (ntintsafe.h)
description: Converts a value of type INT8 to a value of type ULONG_PTR.
old-location: kernel\rtlint8toulongptr.htm
tech.root: kernel
ms.assetid: C406C404-1A6D-4D83-9D71-BC2980C1A84D
ms.date: 04/30/2018
keywords: ["RtlInt8ToULongPtr function"]
ms.keywords: RtlInt8ToULongPtr, RtlInt8ToULongPtr function [Kernel-Mode Driver Architecture], kernel.rtlint8toulongptr, ntintsafe/RtlInt8ToULongPtr
f1_keywords:
 - "ntintsafe/RtlInt8ToULongPtr"
 - "RtlInt8ToULongPtr"
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
- RtlInt8ToULongPtr
targetos: Windows
req.typenames: 
---

# RtlInt8ToULongPtr function


## -description


Converts a value of type <b>INT8</b> to a value of type <b>ULONG_PTR</b>.


## -parameters




### -param i8Operand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt8ToDWordPtr</li>
<li>RtlInt8ToSIZET
</li>
</ul>


