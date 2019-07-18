---
UID: NF:ntintsafe.RtlLongPtrToULong
title: RtlLongPtrToULong function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type ULONG.
old-location: kernel\rtllongptrtoulong.htm
tech.root: kernel
ms.assetid: 3E494420-CB85-4C9C-8052-EBA73B61628C
ms.date: 04/30/2018
ms.keywords: RtlLongPtrToULong, RtlLongPtrToULong function [Kernel-Mode Driver Architecture], kernel.rtllongptrtoulong, ntintsafe/RtlLongPtrToULong
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlLongPtrToULong"
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
- RtlLongPtrToULong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongPtrToULong function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>ULONG</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongPtrToDWord
</li>
<li>RtlSSIZETToULong
</li>
<li>RtlSSIZETToDWord
</li>
</ul>


