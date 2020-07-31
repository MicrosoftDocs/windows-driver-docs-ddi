---
UID: NF:ntintsafe.RtlLongLongToIntPtr
title: RtlLongLongToIntPtr function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type INT_PTR.
old-location: kernel\rtllonglongtointptr.htm
tech.root: kernel
ms.assetid: 7BFAB50B-7C0A-40D8-AB6D-ECBBDA0387AA
ms.date: 04/30/2018
keywords: ["RtlLongLongToIntPtr function"]
ms.keywords: RtlLongLongToIntPtr, RtlLongLongToIntPtr function [Kernel-Mode Driver Architecture], kernel.rtllonglongtointptr, ntintsafe/RtlLongLongToIntPtr
f1_keywords:
 - "ntintsafe/RtlLongLongToIntPtr"
 - "RtlLongLongToIntPtr"
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
- RtlLongLongToIntPtr
targetos: Windows
req.typenames: 
---

# RtlLongLongToIntPtr function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>INT_PTR</b>.


## -parameters




### -param llOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongLongToPtrdiffT
</li>
<li>RtlLong64ToIntPtr
</li>
<li>RtlLong64ToPtrdiffT
</li>
<li>RtlInt64ToIntPtr
</li>
<li>RtlInt64ToPtrdiffT
</li>
</ul>


