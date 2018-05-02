---
UID: NF:ntintsafe.RtlLongPtrToLong
title: RtlLongPtrToLong function
author: windows-driver-content
description: Converts a value of type LONG_PTR to a value of type LONG.
old-location: kernel\rtllongptrtolong.htm
old-project: kernel
ms.assetid: 8BCA0240-FCE7-4C21-B5B4-DEBD87DBDD9D
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlLongPtrToLong, RtlLongPtrToLong function [Kernel-Mode Driver Architecture], kernel.rtllongptrtolong, ntintsafe/RtlLongPtrToLong
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	RtlLongPtrToLong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongPtrToLong function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>LONG</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlSSIZETToLong
</li>
</ul>


