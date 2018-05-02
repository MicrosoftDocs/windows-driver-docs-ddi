---
UID: NF:ntintsafe.RtlInt8ToUChar
title: RtlInt8ToUChar function
author: windows-driver-content
description: Converts a value of type INT8 to a value of type UCHAR.
old-location: kernel\rtlint8touchar.htm
old-project: kernel
ms.assetid: 3E8BF45A-D968-4C9F-8C38-65B39665496B
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlInt8ToUChar, RtlInt8ToUChar function [Kernel-Mode Driver Architecture], kernel.rtlint8touchar, ntintsafe/RtlInt8ToUChar
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
-	RtlInt8ToUChar
product: Windows
targetos: Windows
req.typenames: 
---

# RtlInt8ToUChar function


## -description


Converts a value of type <b>INT8</b> to a value of type <b>UCHAR</b>.


## -parameters




### -param i8Operand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



