---
UID: NF:ntintsafe.RtlLongToULongLong
title: RtlLongToULongLong function (ntintsafe.h)
description: Converts a value of type LONG to a value of type ULONGLONG.
old-location: kernel\rtllongtoulonglong.htm
tech.root: kernel
ms.assetid: 372B00C3-E5BD-4B2B-BB6B-F07878D661B4
ms.date: 04/30/2018
keywords: ["RtlLongToULongLong function"]
ms.keywords: RtlLongToULongLong, RtlLongToULongLong function [Kernel-Mode Driver Architecture], kernel.rtllongtoulonglong, ntintsafe/RtlLongToULongLong
f1_keywords:
 - "ntintsafe/RtlLongToULongLong"
 - "RtlLongToULongLong"
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
- RtlLongToULongLong
targetos: Windows
req.typenames: 
---

# RtlLongToULongLong function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>ULONGLONG</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pullResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToDWordLong
</li>
<li>RtlLongToULong64
</li>
<li>RtlLongToDWord64
</li>
<li>RtlLongToUInt64
</li>
</ul>


