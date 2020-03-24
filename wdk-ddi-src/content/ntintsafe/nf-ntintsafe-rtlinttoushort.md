---
UID: NF:ntintsafe.RtlIntToUShort
title: RtlIntToUShort function (ntintsafe.h)
description: Converts a value of type INT to a value of type USHORT.
old-location: kernel\rtlinttoushort.htm
tech.root: kernel
ms.assetid: 52571477-80F5-4848-8BCC-AFA70140FABE
ms.date: 04/30/2018
keywords: ["RtlIntToUShort function"]
ms.keywords: RtlIntToUShort, RtlIntToUShort function [Kernel-Mode Driver Architecture], kernel.rtlinttoushort, ntintsafe/RtlIntToUShort
f1_keywords:
 - "ntintsafe/RtlIntToUShort"
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
- RtlIntToUShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntToUShort function


## -description


Converts a value of type <b>INT</b> to a value of type <b>USHORT</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntToUInt16
</li>
<li>RtlIntToWord
</li>
<li>RtlInt32ToUShort
</li>
<li>RtlInt32ToUInt16
</li>
<li>RtlInt32ToWord
</li>
</ul>


