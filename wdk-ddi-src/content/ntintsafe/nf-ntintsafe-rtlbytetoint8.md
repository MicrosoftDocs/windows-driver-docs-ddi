---
UID: NF:ntintsafe.RtlByteToInt8
title: RtlByteToInt8 function (ntintsafe.h)
description: Converts a value of type BYTE to a value of type INT8.
old-location: kernel\rtlbytetoint8.htm
tech.root: kernel
ms.assetid: 865E62CA-0D73-4957-88AA-EEF5910AD916
ms.date: 04/30/2018
ms.keywords: RtlByteToInt8, RtlByteToInt8 function [Kernel-Mode Driver Architecture], kernel.rtlbytetoint8, ntintsafe/RtlByteToInt8
f1_keywords:
 - "ntintsafe/RtlByteToInt8"
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
- RtlByteToInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlByteToInt8 function


## -description


Converts a value of type <b>BYTE</b> to a value of type <b>INT8</b>.


## -parameters




### -param bOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



