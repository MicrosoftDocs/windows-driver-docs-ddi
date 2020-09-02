---
UID: NF:ntintsafe.RtlULongLongToChar
title: RtlULongLongToChar function (ntintsafe.h)
description: Converts a value of type ULONGLONG to a value of type CHAR.
old-location: kernel\rtlulonglongtochar.htm
tech.root: kernel
ms.assetid: 8C6356A2-9E4A-4654-9FB3-EC11894A24AB
ms.date: 04/30/2018
keywords: ["RtlULongLongToChar function"]
ms.keywords: RtlULongLongToChar, RtlULongLongToChar function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtochar, ntintsafe/RtlULongLongToChar
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlULongLongToChar
 - ntintsafe/RtlULongLongToChar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongLongToChar
---

# RtlULongLongToChar function


## -description

Converts a value of type <b>ULONGLONG</b> to a value of type <b>CHAR</b>.

## -parameters

### -param ullOperand 

[in]
The value to be converted.

### -param pch 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

