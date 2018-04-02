---
UID: NF:ntintsafe.RtlIntPtrToInt
title: RtlIntPtrToInt function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type INT.
old-location: kernel\rtlintptrtoint.htm
old-project: kernel
ms.assetid: 96D932C6-B969-4C91-B4B1-6FEC7D4AD250
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlIntPtrToInt, RtlIntPtrToInt function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoint, ntintsafe/RtlIntPtrToInt
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
-	RtlIntPtrToInt
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntPtrToInt function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>INT</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToInt32
</li>
<li>RtlPtrdiffTToInt
</li>
<li>RtlPtrdiffTToInt32
</li>
</ul>


