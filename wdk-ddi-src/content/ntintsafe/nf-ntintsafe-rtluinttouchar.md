---
UID: NF:ntintsafe.RtlUIntToUChar
title: RtlUIntToUChar function
author: windows-driver-content
description: Converts a value of type UINT to a value of type UCHAR.
old-location: kernel\rtluinttouchar.htm
old-project: kernel
ms.assetid: E47C3DA7-C9DD-47C6-A652-05D85989C85F
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUIntToUChar, RtlUIntToUChar function [Kernel-Mode Driver Architecture], kernel.rtluinttouchar, ntintsafe/RtlUIntToUChar
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
-	RtlUIntToUChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntToUChar function


## -description


Converts a value of type <b>UINT</b> to a value of type <b>UCHAR</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUInt32ToChar
</li>
</ul>


