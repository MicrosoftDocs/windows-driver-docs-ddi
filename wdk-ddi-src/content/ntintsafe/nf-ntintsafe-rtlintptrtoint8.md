---
UID: NF:ntintsafe.RtlIntPtrToInt8
title: RtlIntPtrToInt8 function (ntintsafe.h)
description: Converts a value of type INT_PTR to a value of type INT8.
old-location: kernel\rtlintptrtoint8.htm
tech.root: kernel
ms.assetid: 3AF29469-C376-4EF7-B8A0-88ADCA8FEE4F
ms.date: 04/30/2018
ms.keywords: RtlIntPtrToInt8, RtlIntPtrToInt8 function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoint8, ntintsafe/RtlIntPtrToInt8
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlIntPtrToInt8"
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
- RtlIntPtrToInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntPtrToInt8 function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>INT8</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlPtrdiffTToInt8</li>
</ul>


