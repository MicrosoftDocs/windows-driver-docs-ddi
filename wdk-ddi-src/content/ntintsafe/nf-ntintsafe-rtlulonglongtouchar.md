---
UID: NF:ntintsafe.RtlULongLongToUChar
title: RtlULongLongToUChar function (ntintsafe.h)
description: Converts a value of type ULONGLONG to a value of type UCHAR.
old-location: kernel\rtlulonglongtouchar.htm
tech.root: kernel
ms.assetid: 3A701A1B-257F-42C4-80A7-8CFF0DAD1A83
ms.date: 04/30/2018
keywords: ["RtlULongLongToUChar function"]
ms.keywords: RtlULongLongToUChar, RtlULongLongToUChar function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtouchar, ntintsafe/RtlULongLongToUChar
f1_keywords:
 - "ntintsafe/RtlULongLongToUChar"
 - "RtlULongLongToUChar"
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
- RtlULongLongToUChar
targetos: Windows
req.typenames: 
---

# RtlULongLongToUChar function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>UCHAR</b>.


## -parameters




### -param ullOperand 
[in]
The value to be converted.


### -param pch 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



