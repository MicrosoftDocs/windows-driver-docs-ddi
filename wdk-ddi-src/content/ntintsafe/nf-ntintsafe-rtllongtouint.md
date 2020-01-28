---
UID: NF:ntintsafe.RtlLongToUInt
title: RtlLongToUInt function (ntintsafe.h)
description: Converts a value of type LONG to a value of type UINT.
old-location: kernel\rtllongtouint.htm
tech.root: kernel
ms.assetid: 8347581C-91CB-4C53-91C5-9560CC88A4B8
ms.date: 04/30/2018
ms.keywords: RtlLongToUInt, RtlLongToUInt function [Kernel-Mode Driver Architecture], kernel.rtllongtouint, ntintsafe/RtlLongToUInt
f1_keywords:
 - "ntintsafe/RtlLongToUInt"
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
- RtlLongToUInt
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongToUInt function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>UINT</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToUInt32
</li>
<li>RtlLongToUIntPtr
</li>
</ul>


