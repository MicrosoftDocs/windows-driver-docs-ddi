---
UID: NF:ntintsafe.RtlULongLongToULong
title: RtlULongLongToULong function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type ULONG.
old-location: kernel\rtlulonglongtoulong.htm
old-project: kernel
ms.assetid: 322A17F1-E767-44EF-837D-F9162C2D5237
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlULongLongToULong, RtlULongLongToULong function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtoulong, ntintsafe/RtlULongLongToULong
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
-	RtlULongLongToULong
product: Windows
targetos: Windows
req.typenames: 
---

# RtlULongLongToULong function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>ULONG</b>.


## -parameters




### -param ullOperand [in]

The value to be converted.


### -param pulResult

TBD




#### - puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



