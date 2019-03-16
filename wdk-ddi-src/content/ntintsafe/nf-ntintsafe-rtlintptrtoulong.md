---
UID: NF:ntintsafe.RtlIntPtrToULong
title: RtlIntPtrToULong function (ntintsafe.h)
description: Converts a value of type INT_PTR to a value of type ULONG.
old-location: kernel\rtlintptrtoulong.htm
tech.root: kernel
ms.assetid: 755F23FE-12F8-4A14-B2E2-746774B86342
ms.date: 04/30/2018
ms.keywords: RtlIntPtrToULong, RtlIntPtrToULong function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoulong, ntintsafe/RtlIntPtrToULong
ms.topic: function
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
- RtlIntPtrToULong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntPtrToULong function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>ULONG</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToDWord
</li>
<li>RtlPtrdiffTToULong
</li>
<li>RtlPtrdiffTToDWord
</li>
</ul>


