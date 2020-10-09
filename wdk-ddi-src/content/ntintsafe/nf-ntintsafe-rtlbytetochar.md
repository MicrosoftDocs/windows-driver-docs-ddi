---
UID: NF:ntintsafe.RtlByteToChar
title: RtlByteToChar function (ntintsafe.h)
description: Converts a value of type BYTE to a value of type CHAR.
old-location: kernel\rtlbytetochar.htm
tech.root: kernel
ms.assetid: A571B2C7-F97E-4717-AA22-D25DE47469E8
ms.date: 04/30/2018
keywords: ["RtlByteToChar function"]
ms.keywords: RtlByteToChar, RtlByteToChar function [Kernel-Mode Driver Architecture], kernel.rtlbytetochar, ntintsafe/RtlByteToChar
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
 - RtlByteToChar
 - ntintsafe/RtlByteToChar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlByteToChar
---

# RtlByteToChar function


## -description

Converts a value of type <b>BYTE</b> to a value of type <b>CHAR</b>.

## -parameters

### -param bOperand 

[in]
The value to be converted.

### -param pch 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

