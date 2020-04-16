---
UID: NF:ntintsafe.RtlIntPtrToUInt8
title: RtlIntPtrToUInt8 function (ntintsafe.h)
description: Converts a value of type INT_PTR to a value of type UINT8.
old-location: kernel\rtlintptrtouint8.htm
tech.root: kernel
ms.assetid: E51696DD-17CE-41F1-AD30-30AB93C81D05
ms.date: 04/30/2018
keywords: ["RtlIntPtrToUInt8 function"]
ms.keywords: RtlIntPtrToUInt8, RtlIntPtrToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtlintptrtouint8, ntintsafe/RtlIntPtrToUInt8
f1_keywords:
 - "ntintsafe/RtlIntPtrToUInt8"
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
- RtlIntPtrToUInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntPtrToUInt8 function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>UINT8</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pui8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToByte
</li>
<li>RtlPtrdiffTToUInt8
</li>
<li>RtlPtrdiffTToByte
</li>
</ul>


