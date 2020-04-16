---
UID: NF:ntintsafe.RtlIntToInt8
title: RtlIntToInt8 function (ntintsafe.h)
description: Converts a value of type INT to a value of type INT8.
old-location: kernel\rtlinttoint8.htm
tech.root: kernel
ms.assetid: ABE24C02-22C3-4F0A-B874-3079F70CA748
ms.date: 04/30/2018
keywords: ["RtlIntToInt8 function"]
ms.keywords: RtlIntToInt8, RtlIntToInt8 function [Kernel-Mode Driver Architecture], kernel.rtlinttoint8, ntintsafe/RtlIntToInt8
f1_keywords:
 - "ntintsafe/RtlIntToInt8"
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
- RtlIntToInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntToInt8 function


## -description


Converts a value of type <b>INT</b> to a value of type <b>INT8</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt32ToInt8
</li>
</ul>


