---
UID: NF:ntintsafe.RtlLongToShort
title: RtlLongToShort function (ntintsafe.h)
description: Converts a value of type LONG to a value of type SHORT.
old-location: kernel\rtllongtoshort.htm
tech.root: kernel
ms.assetid: FDFEADE6-CD33-4C04-972B-3E31C43E730A
ms.date: 04/30/2018
keywords: ["RtlLongToShort function"]
ms.keywords: RtlLongToShort, RtlLongToShort function [Kernel-Mode Driver Architecture], kernel.rtllongtoshort, ntintsafe/RtlLongToShort
f1_keywords:
 - "ntintsafe/RtlLongToShort"
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
- RtlLongToShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongToShort function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>SHORT</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToInt16
</li>
</ul>


