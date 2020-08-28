---
UID: NF:ntintsafe.RtlInt8ToULong
title: RtlInt8ToULong function (ntintsafe.h)
description: Converts a value of type INT8 to a value of type ULONG.
old-location: kernel\rtlint8toulong.htm
tech.root: kernel
ms.assetid: 2C5FA0DA-5517-4BB6-A106-D8A20EDB5D46
ms.date: 04/30/2018
keywords: ["RtlInt8ToULong function"]
ms.keywords: RtlInt8ToULong, RtlInt8ToULong function [Kernel-Mode Driver Architecture], kernel.rtlint8toulong, ntintsafe/RtlInt8ToULong
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
 - RtlInt8ToULong
 - ntintsafe/RtlInt8ToULong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlInt8ToULong
---

# RtlInt8ToULong function


## -description

Converts a value of type <b>INT8</b> to a value of type <b>ULONG</b>.

## -parameters

### -param i8Operand 

[in]
The value to be converted.

### -param pulResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt8ToDWord</li>
</ul>

