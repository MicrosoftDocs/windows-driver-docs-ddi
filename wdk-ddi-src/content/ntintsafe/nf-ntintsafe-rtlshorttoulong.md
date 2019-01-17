---
UID: NF:ntintsafe.RtlShortToULong
title: RtlShortToULong function
description: Converts a value of type SHORT to a value of type ULONG.
old-location: kernel\rtlshorttoulong.htm
tech.root: kernel
ms.assetid: A69F7F0E-3A71-4F29-9B56-A9B34D112F6C
ms.date: 04/30/2018
ms.keywords: RtlShortToULong, RtlShortToULong function [Kernel-Mode Driver Architecture], kernel.rtlshorttoulong, ntintsafe/RtlShortToULong
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlShortToULong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlShortToULong function


## -description


Converts a value of type <b>SHORT</b> to a value of type <b>ULONG</b>.


## -parameters




### -param sOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlShortToDWord
</li>
<li>RtlInt16ToULong
</li>
<li>RtlInt16ToDWord
</li>
</ul>


