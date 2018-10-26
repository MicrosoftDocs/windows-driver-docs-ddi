---
UID: NF:ntintsafe.RtlUIntToUInt8
title: RtlUIntToUInt8 function
author: windows-driver-content
description: Converts a value of type UINT to a value of type UINT8.
old-location: kernel\rtluinttouint8.htm
tech.root: kernel
ms.assetid: 39D4AE72-EF60-455E-A7C2-F2896E304897
ms.date: 04/30/2018
ms.keywords: RtlUIntToUInt8, RtlUIntToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtluinttouint8, ntintsafe/RtlUIntToUInt8
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
-	RtlUIntToUInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntToUInt8 function


## -description


Converts a value of type <b>UINT</b> to a value of type <b>UINT8</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pui8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlUIntToByte
</li>
<li>RtlUInt32ToUInt8
</li>
</ul>


