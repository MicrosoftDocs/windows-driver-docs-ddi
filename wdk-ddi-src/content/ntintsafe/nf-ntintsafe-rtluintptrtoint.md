---
UID: NF:ntintsafe.RtlUIntPtrToInt
title: RtlUIntPtrToInt function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type INT.
old-location: kernel\rtluintptrtoint.htm
old-project: kernel
ms.assetid: C33B717D-0874-47AB-8503-D6F82F713CBF
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUIntPtrToInt, RtlUIntPtrToInt function [Kernel-Mode Driver Architecture], kernel.rtluintptrtoint, ntintsafe/RtlUIntPtrToInt
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
-	RtlUIntPtrToInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntPtrToInt function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>INT</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToInt32
</li>
<li>RtlSizeTToInt
</li>
<li>RtlSizeTToInt32
</li>
</ul>


