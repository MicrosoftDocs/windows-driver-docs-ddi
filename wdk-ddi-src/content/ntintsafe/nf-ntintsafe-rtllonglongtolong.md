---
UID: NF:ntintsafe.RtlLongLongToLong
title: RtlLongLongToLong function
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type LONG.
old-location: kernel\rtllonglongtolong.htm
tech.root: kernel
ms.assetid: B4E5BDF1-CB9A-4919-A73D-E660D2847470
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlLongLongToLong, RtlLongLongToLong function [Kernel-Mode Driver Architecture], kernel.rtllonglongtolong, ntintsafe/RtlLongLongToLong
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
-	RtlLongLongToLong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongLongToLong function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>LONG</b>.


## -parameters




### -param llOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlIntPtrToLong
</li>
<li>RtlLongPtrToLong
</li>
<li>RtlLongLongToLongPtr
</li>
<li>RtlLong64ToLong
</li>
<li>RtlInt64ToLong
</li>
</ul>


