---
UID: NF:ntintsafe.RtlUIntPtrToUInt16
title: RtlUIntPtrToUInt16 function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type UINT16.
old-location: kernel\rtluintptrtouint16.htm
tech.root: kernel
ms.assetid: 405FB676-64FD-43DE-BCD9-233C8B43D851
ms.date: 04/30/2018
keywords: ["RtlUIntPtrToUInt16 function"]
ms.keywords: RtlUIntPtrToUInt16, RtlUIntPtrToUInt16 function [Kernel-Mode Driver Architecture], kernel.rtluintptrtouint16, ntintsafe/RtlUIntPtrToUInt16
f1_keywords:
 - "ntintsafe/RtlUIntPtrToUInt16"
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
- RtlUIntPtrToUInt16
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToUInt16 function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>UINT16</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pu16Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



