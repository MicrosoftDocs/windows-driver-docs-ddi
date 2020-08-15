---
UID: NF:ntintsafe.RtlULongLongToLong
title: RtlULongLongToLong function (ntintsafe.h)
description: Converts a value of type ULONGLONG to a value of type LONG.
old-location: kernel\rtlulonglongtolong.htm
tech.root: kernel
ms.assetid: DC1784C6-0775-46E9-A439-B522713C297C
ms.date: 04/30/2018
keywords: ["RtlULongLongToLong function"]
ms.keywords: RtlULongLongToLong, RtlULongLongToLong function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtolong, ntintsafe/RtlULongLongToLong
f1_keywords:
 - "ntintsafe/RtlULongLongToLong"
 - "RtlULongLongToLong"
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
- RtlULongLongToLong
targetos: Windows
req.typenames: 
---

# RtlULongLongToLong function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>LONG</b>.


## -parameters




### -param ullOperand 
[in]
The value to be converted.


### -param plResult 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



