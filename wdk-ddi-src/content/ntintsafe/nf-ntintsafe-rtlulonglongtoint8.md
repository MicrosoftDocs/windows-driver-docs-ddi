---
UID: NF:ntintsafe.RtlULongLongToInt8
title: RtlULongLongToInt8 function (ntintsafe.h)
description: Converts a value of type ULONGLONG to a value of type INT8.
old-location: kernel\rtlulonglongtoint8.htm
tech.root: kernel
ms.assetid: 9427C33F-F670-4E2C-B3C0-1FACA9AD6387
ms.date: 04/30/2018
keywords: ["RtlULongLongToInt8 function"]
ms.keywords: RtlULongLongToInt8, RtlULongLongToInt8 function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtoint8, ntintsafe/RtlULongLongToInt8
f1_keywords:
 - "ntintsafe/RtlULongLongToInt8"
 - "RtlULongLongToInt8"
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
- RtlULongLongToInt8
targetos: Windows
req.typenames: 
---

# RtlULongLongToInt8 function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>INT8</b>.


## -parameters




### -param ullOperand 
[in]
The value to be converted.


### -param pi8Result 
[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



