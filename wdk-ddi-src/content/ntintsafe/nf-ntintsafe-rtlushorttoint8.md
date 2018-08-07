---
UID: NF:ntintsafe.RtlUShortToInt8
title: RtlUShortToInt8 function
author: windows-driver-content
description: Converts a value of type USHORT to a value of type INT8.
old-location: kernel\rtlushorttoint8.htm
tech.root: kernel
ms.assetid: 789AC84A-E271-4048-86F7-32EA5A966D71
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlUShortToInt8, RtlUShortToInt8 function [Kernel-Mode Driver Architecture], kernel.rtlushorttoint8, ntintsafe/RtlUShortToInt8
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
-	RtlUShortToInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUShortToInt8 function


## -description


Converts a value of type <b>USHORT</b> to a value of type <b>INT8</b>.


## -parameters




### -param usOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



