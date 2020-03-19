---
UID: NF:ntintsafe.RtlLongLongToShort
title: RtlLongLongToShort function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type SHORT.
old-location: kernel\rtllonglongtoshort.htm
tech.root: kernel
ms.assetid: F9FCB214-D56A-4BCC-BB7A-40833836D333
ms.date: 04/30/2018
keywords: ["RtlLongLongToShort function"]
ms.keywords: RtlLongLongToShort, RtlLongLongToShort function [Kernel-Mode Driver Architecture], kernel.rtllonglongtoshort, ntintsafe/RtlLongLongToShort
f1_keywords:
 - "ntintsafe/RtlLongLongToShort"
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
- RtlLongLongToShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongLongToShort function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>SHORT</b>.


## -parameters




### -param llOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongLongToInt16
</li>
<li>RtlLong64ToShort
</li>
<li>RtlLong64ToInt16
</li>
<li>RtlInt64ToShort
</li>
<li>RtlInt64ToInt16
</li>
</ul>


