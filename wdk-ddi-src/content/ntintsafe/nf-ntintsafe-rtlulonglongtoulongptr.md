---
UID: NF:ntintsafe.RtlULongLongToULongPtr
title: RtlULongLongToULongPtr function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type ULONG_PTR.
old-location: kernel\rtlulonglongtoulongptr.htm
old-project: kernel
ms.assetid: D170649F-D0CE-454B-8F2B-18C66F58CAF7
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlULongLongToULongPtr, RtlULongLongToULongPtr function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtoulongptr, ntintsafe/RtlULongLongToULongPtr
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
-	RtlULongLongToULongPtr
product: Windows
targetos: Windows
req.typenames: 
---

# RtlULongLongToULongPtr function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>ULONG_PTR</b>.


## -parameters




### -param ullOperand [in]

The value to be converted.


### -param pulResult

TBD




#### - puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



