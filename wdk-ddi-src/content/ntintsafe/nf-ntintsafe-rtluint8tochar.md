---
UID: NF:ntintsafe.RtlUInt8ToChar
title: RtlUInt8ToChar function (ntintsafe.h)
description: Converts a value of type UINT8 to a value of type CHAR.
old-location: kernel\rtluint8tochar.htm
tech.root: kernel
ms.assetid: 78EAB56F-8E6D-4048-83DC-1B9BC75E08B5
ms.date: 04/30/2018
ms.keywords: RtlUInt8ToChar, RtlUInt8ToChar function [Kernel-Mode Driver Architecture], kernel.rtluint8tochar, ntintsafe/RtlUInt8ToChar
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlUInt8ToChar"
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
- RtlUInt8ToChar
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUInt8ToChar function


## -description


Converts a value of type <b>UINT8</b> to a value of type <b>CHAR</b>.


## -parameters




### -param u8Operand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



