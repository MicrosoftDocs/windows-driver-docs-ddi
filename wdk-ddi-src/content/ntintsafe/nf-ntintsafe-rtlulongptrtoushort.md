---
UID: NF:ntintsafe.RtlULongPtrToUShort
title: RtlULongPtrToUShort function (ntintsafe.h)
description: Converts a value of type ULONG_PTR to a value of type USHORT.
old-location: kernel\rtlulongptrtoushort.htm
tech.root: kernel
ms.assetid: 444A0D3B-AEC3-4474-949F-6C62F54DA43A
ms.date: 04/30/2018
keywords: ["RtlULongPtrToUShort function"]
ms.keywords: RtlULongPtrToUShort, RtlULongPtrToUShort function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtoushort, ntintsafe/RtlULongPtrToUShort
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
 - RtlULongPtrToUShort
 - ntintsafe/RtlULongPtrToUShort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongPtrToUShort
---

# RtlULongPtrToUShort function


## -description

Converts a value of type <b>ULONG_PTR</b> to a value of type <b>USHORT</b>.

## -parameters

### -param ulOperand 

[in]
The value to be converted.

### -param pusResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

