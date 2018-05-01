---
UID: NF:ntintsafe.RtlUInt8ToInt8
title: RtlUInt8ToInt8 function
author: windows-driver-content
description: Converts a value of type UINT8 to a value of type INT8.
old-location: kernel\rtluint8toint8.htm
old-project: kernel
ms.assetid: 92666A78-DC2C-4B0B-B5D3-E724F342D151
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlUInt8ToInt8, RtlUInt8ToInt8 function [Kernel-Mode Driver Architecture], kernel.rtluint8toint8, ntintsafe/RtlUInt8ToInt8
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
-	RtlUInt8ToInt8
product: Windows
targetos: Windows
req.typenames: 
---

# RtlUInt8ToInt8 function


## -description


Converts a value of type <b>UINT8</b> to a value of type <b>INT8</b>.


## -parameters




### -param u8Operand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



