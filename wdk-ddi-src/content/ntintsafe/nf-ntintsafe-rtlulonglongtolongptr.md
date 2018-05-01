---
UID: NF:ntintsafe.RtlULongLongToLongPtr
title: RtlULongLongToLongPtr function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type LONG_PTR.
old-location: kernel\rtlulonglongtolongptr.htm
old-project: kernel
ms.assetid: 986178DA-7F3D-4178-BF24-E99B14E6DD36
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlULongLongToLongPtr, RtlULongLongToLongPtr function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtolongptr, ntintsafe/RtlULongLongToLongPtr
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
-	RtlULongLongToLongPtr
product: Windows
targetos: Windows
req.typenames: 
---

# RtlULongLongToLongPtr function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>LONG_PTR</b>.


## -parameters




### -param ullOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlULongLongToSSIZET
</li>
<li>RtlDWordLongToLongPtr
</li>
<li>RtlDWordLongToSSIZET
</li>
<li>RtlULong64ToLongPtr
</li>
<li>RtlULong64ToSSIZET
</li>
<li>RtlDWord64ToLongPtr
</li>
<li>RtlDWord64ToSSIZET
</li>
<li>RtlUInt64ToLongPtr
</li>
<li>RtlUInt64ToSSIZET
</li>
</ul>


