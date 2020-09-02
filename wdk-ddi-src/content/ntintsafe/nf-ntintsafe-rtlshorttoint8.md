---
UID: NF:ntintsafe.RtlShortToInt8
title: RtlShortToInt8 function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type INT8.
old-location: kernel\rtlshorttoint8.htm
tech.root: kernel
ms.assetid: 644559BB-9842-4261-9A9C-720185E6E9F4
ms.date: 04/30/2018
keywords: ["RtlShortToInt8 function"]
ms.keywords: RtlShortToInt8, RtlShortToInt8 function [Kernel-Mode Driver Architecture], kernel.rtlshorttoint8, ntintsafe/RtlShortToInt8
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
 - RtlShortToInt8
 - ntintsafe/RtlShortToInt8
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlShortToInt8
---

# RtlShortToInt8 function


## -description

Converts a value of type <b>SHORT</b> to a value of type <b>INT8</b>.

## -parameters

### -param sOperand 

[in]
The value to be converted.

### -param pi8Result 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt16ToInt8
</li>
</ul>

