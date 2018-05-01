---
UID: NF:ntintsafe.RtlIntToUInt8
title: RtlIntToUInt8 function
author: windows-driver-content
description: Converts a value of type INT to a value of type UINT8.
old-location: kernel\rtlinttouint8.htm
old-project: kernel
ms.assetid: BD5F605A-0E0F-4D68-8905-6FCEC9DD7F15
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlIntToUInt8, RtlIntToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtlinttouint8, ntintsafe/RtlIntToUInt8
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
-	RtlIntToUInt8
product: Windows
targetos: Windows
req.typenames: 
---

# RtlIntToUInt8 function


## -description


Converts a value of type <b>INT</b> to a value of type <b>UINT8</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pui8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntToByte
</li>
<li>RtlInt32ToByte
</li>
<li>RtlInt32ToUInt8
</li>
</ul>


