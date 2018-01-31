---
UID: NF:ntintsafe.RtlULongToInt
title: RtlULongToInt function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type INT.
old-location: kernel\rtlulongtoint.htm
old-project: kernel
ms.assetid: E6233C9B-92DF-4524-8C9D-4FED7C4BB3FC
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlulongtoint, ntintsafe/RtlULongToInt, RtlULongToInt, RtlULongToInt function [Kernel-Mode Driver Architecture]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntintsafe.h
apiname:
-	RtlULongToInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongToInt function


## -description


Converts a value of type <b>ULONG</b> to a value of type <b>INT</b>.


## -syntax


````
NTSTATUS RtlULongToInt(
  _In_  ULONG ulOperand,
  _Out_ INT   *piResult
);
````


## -parameters




#### - ulOperand [in]

The value to be converted.


#### - piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


