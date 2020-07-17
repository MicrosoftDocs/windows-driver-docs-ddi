---
UID: NF:ntintsafe.RtlLongPtrToUShort
title: RtlLongPtrToUShort function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type USHORT.
old-location: kernel\rtllongptrtoushort.htm
tech.root: kernel
ms.assetid: B003772E-9A9A-4EE0-BF8F-C956BCE7EDA5
ms.date: 04/30/2018
keywords: ["RtlLongPtrToUShort function"]
ms.keywords: RtlLongPtrToUShort, RtlLongPtrToUShort function [Kernel-Mode Driver Architecture], kernel.rtllongptrtoushort, ntintsafe/RtlLongPtrToUShort
f1_keywords:
 - "ntintsafe/RtlLongPtrToUShort"
 - "RtlLongPtrToUShort"
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
- RtlLongPtrToUShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongPtrToUShort function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>USHORT</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongPtrToUInt16
</li>
<li>RtlLongPtrToWord
</li>
<li>RtlSSIZETToUShort
</li>
<li>RtlSSIZETToUInt16
</li>
<li>RtlSSIZETToWord
</li>
</ul>


