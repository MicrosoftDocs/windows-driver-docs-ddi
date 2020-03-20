---
UID: NF:ntintsafe.RtlUIntToInt8
title: RtlUIntToInt8 function (ntintsafe.h)
description: Converts a value of type UINT to a value of type INT8.
old-location: kernel\rtluinttoint8.htm
tech.root: kernel
ms.assetid: 8E9CA6F9-D0F1-4315-8A1B-CFA46B8458D7
ms.date: 04/30/2018
keywords: ["RtlUIntToInt8 function"]
ms.keywords: RtlUIntToInt8, RtlUIntToInt8 function [Kernel-Mode Driver Architecture], kernel.rtluinttoint8, ntintsafe/RtlUIntToInt8
f1_keywords:
 - "ntintsafe/RtlUIntToInt8"
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
- RtlUIntToInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntToInt8 function


## -description


Converts a value of type <b>UINT</b> to a value of type <b>INT8</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



