---
UID: NF:ntintsafe.RtlUIntToInt8
title: RtlUIntToInt8 function
author: windows-driver-content
description: Converts a value of type UINT to a value of type INT8.
old-location: kernel\rtluinttoint8.htm
old-project: kernel
ms.assetid: 8E9CA6F9-D0F1-4315-8A1B-CFA46B8458D7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 8, I, R, RtlUIntToInt8, RtlUIntToInt8 function [Kernel-Mode Driver Architecture], T, U, kernel.rtluinttoint8, l, n, ntintsafe/RtlUIntToInt8, o, t"
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
-	RtlUIntToInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntToInt8 function


## -description


Converts a value of type <b>UINT</b> to a value of type <b>INT8</b>.


## -syntax


````
NTSTATUS RtlUIntToInt8(
  _In_  UINT uOperand,
  _Out_ INT8 *pi8Result
);
````


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



