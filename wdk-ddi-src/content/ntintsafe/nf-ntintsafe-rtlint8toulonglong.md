---
UID: NF:ntintsafe.RtlInt8ToULongLong
title: RtlInt8ToULongLong function (ntintsafe.h)
description: Converts a value of type INT8 to a value of type ULONGLONG.
old-location: kernel\rtlint8toulonglong.htm
tech.root: kernel
ms.assetid: C840CDA4-36C8-4D7C-88EB-19292429C45C
ms.date: 04/30/2018
ms.keywords: RtlInt8ToULongLong, RtlInt8ToULongLong function [Kernel-Mode Driver Architecture], kernel.rtlint8toulonglong, ntintsafe/RtlInt8ToULongLong
f1_keywords:
 - "ntintsafe/RtlInt8ToULongLong"
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
- RtlInt8ToULongLong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInt8ToULongLong function


## -description


Converts a value of type <b>INT8</b> to a value of type <b>ULONGLONG</b>.


## -parameters




### -param i8Operand [in]

The value to be converted.


### -param pullResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt8ToDWordLong</li>
<li>
RtlInt8ToULong64</li>
<li>
RtlInt8ToDWord64</li>
<li>
RtlInt8ToUInt64
</li>
</ul>


