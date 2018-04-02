---
UID: NF:ntintsafe.RtlIntToUInt
title: RtlIntToUInt function
author: windows-driver-content
description: Converts a value of type INT to a value of type UINT.
old-location: kernel\rtlinttouint.htm
old-project: kernel
ms.assetid: 9D2C7E0F-99E2-4B95-8CB6-9158DA1D906F
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlIntToUInt, RtlIntToUInt function [Kernel-Mode Driver Architecture], kernel.rtlinttouint, ntintsafe/RtlIntToUInt
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
-	RtlIntToUInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntToUInt function


## -description


Converts a value of type <b>INT</b> to a value of type <b>UINT</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntToUIntPtr
</li>
<li>RtlInt32ToUInt
</li>
<li>RtlInt32ToUInt32
</li>
<li>RtlIntToSizeT
</li>
<li>RtlInt32ToUIntPtr
</li>
<li>RtlInt32ToSizeT
</li>
</ul>


