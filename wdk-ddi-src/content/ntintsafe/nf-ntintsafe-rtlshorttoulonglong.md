---
UID: NF:ntintsafe.RtlShortToULongLong
title: RtlShortToULongLong function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type ULONGLONG.
old-location: kernel\rtlshorttoulonglong.htm
tech.root: kernel
ms.assetid: DC25A607-F329-44F2-8D26-A6F7E3050A33
ms.date: 04/30/2018
keywords: ["RtlShortToULongLong function"]
ms.keywords: RtlShortToULongLong, RtlShortToULongLong function [Kernel-Mode Driver Architecture], kernel.rtlshorttoulonglong, ntintsafe/RtlShortToULongLong
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
 - RtlShortToULongLong
 - ntintsafe/RtlShortToULongLong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlShortToULongLong
---

# RtlShortToULongLong function


## -description

Converts a value of type <b>SHORT</b> to a value of type <b>ULONGLONG</b>.

## -parameters

### -param sOperand 

[in]
The value to be converted.

### -param pullResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlShortToDWordLong
</li>
<li>RtlShortToULong64
</li>
<li>RtlShortToDWord64
</li>
<li>RtlShortToUInt64
</li>
<li>RtlInt16ToULongLong</li>
<li>RtlInt16ToDWordLong</li>
<li>

RtlInt16ToULong64
</li>
<li>RtlInt16ToDWord64
</li>
<li>RtlInt16ToUInt64
</li>
</ul>

