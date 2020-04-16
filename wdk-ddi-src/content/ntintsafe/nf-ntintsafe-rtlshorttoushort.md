---
UID: NF:ntintsafe.RtlShortToUShort
title: RtlShortToUShort function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type USHORT.
old-location: kernel\rtlshorttoushort.htm
tech.root: kernel
ms.assetid: 6FD7C994-822A-422C-82D8-768BA842B2B2
ms.date: 04/30/2018
keywords: ["RtlShortToUShort function"]
ms.keywords: RtlShortToUShort, RtlShortToUShort function [Kernel-Mode Driver Architecture], kernel.rtlshorttoushort, ntintsafe/RtlShortToUShort
f1_keywords:
 - "ntintsafe/RtlShortToUShort"
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
- RtlShortToUShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlShortToUShort function


## -description


Converts a value of type <b>SHORT</b> to a value of type <b>USHORT</b>.


## -parameters




### -param sOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlShortToUInt16
</li>
<li>RtlShortToWord
</li>
<li>RtlInt16ToUShort
</li>
<li>RtlInt16ToUInt16
</li>
<li>RtlInt16ToWord
</li>
</ul>


