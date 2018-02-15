---
UID: NF:ntintsafe.RtlLongToInt8
title: RtlLongToInt8 function
author: windows-driver-content
description: Converts a value of type LONG to a value of type INT8.
old-location: kernel\rtllongtoint8.htm
old-project: kernel
ms.assetid: 38BE4F80-DEF2-486B-8A37-BCFD7626325D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongToInt8, ntintsafe/RtlLongToInt8, RtlLongToInt8 function [Kernel-Mode Driver Architecture], kernel.rtllongtoint8
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
-	RtlLongToInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToInt8 function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>INT8</b>.


## -syntax


````
NTSTATUS RtlLongToInt8(
  _In_  LONG lOperand,
  _Out_ INT8 *pi8Result
);
````


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



