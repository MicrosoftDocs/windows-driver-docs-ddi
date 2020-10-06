---
UID: NF:ntintsafe.RtlLongLongToUChar
title: RtlLongLongToUChar function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type UCHAR.
old-location: kernel\rtllonglongtouchar.htm
tech.root: kernel
ms.assetid: 58380931-F16E-478D-8C1B-690CF90C4BD0
ms.date: 04/30/2018
keywords: ["RtlLongLongToUChar function"]
ms.keywords: RtlLongLongToUChar, RtlLongLongToUChar function [Kernel-Mode Driver Architecture], kernel.rtllonglongtouchar, ntintsafe/RtlLongLongToUChar
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
 - RtlLongLongToUChar
 - ntintsafe/RtlLongLongToUChar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongLongToUChar
---

# RtlLongLongToUChar function


## -description

Converts a value of type <b>LONGLONG</b> to a value of type <b>UCHAR</b>.

## -parameters

### -param llOperand 

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

This function uses the following alternate name:

<ul>
<li>
RtlLong64ToUChar
</li>
<li>RtlInt64ToUChar
</li>
</ul>

