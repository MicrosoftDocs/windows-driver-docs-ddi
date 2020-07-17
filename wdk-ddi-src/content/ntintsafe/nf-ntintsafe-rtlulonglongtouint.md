---
UID: NF:ntintsafe.RtlULongLongToUInt
title: RtlULongLongToUInt function (ntintsafe.h)
description: Converts a value of type ULONGLONG to a value of type UINT.
old-location: kernel\rtlulonglongtouint.htm
tech.root: kernel
ms.assetid: CC69FD37-27DE-47AD-B509-DB659B906248
ms.date: 04/30/2018
keywords: ["RtlULongLongToUInt function"]
ms.keywords: RtlULongLongToUInt, RtlULongLongToUInt function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtouint, ntintsafe/RtlULongLongToUInt
f1_keywords:
 - "ntintsafe/RtlULongLongToUInt"
 - "RtlULongLongToUInt"
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
- RtlULongLongToUInt
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongLongToUInt function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>UINT</b>.


## -parameters




### -param ullOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



