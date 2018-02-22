---
UID: NF:ntintsafe.RtlULongLongToInt8
title: RtlULongLongToInt8 function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type INT8.
old-location: kernel\rtlulonglongtoint8.htm
old-project: kernel
ms.assetid: 9427C33F-F670-4E2C-B3C0-1FACA9AD6387
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlULongLongToInt8, kernel.rtlulonglongtoint8, RtlULongLongToInt8 function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongLongToInt8
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
-	RtlULongLongToInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongLongToInt8 function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>INT8</b>.


## -syntax


````
NTSTATUS RtlULongLongToInt8(
  _In_  ULONGLONG ullOperand,
  _Out_ INT8      *pi8Result
);
````


## -parameters




### -param ullOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



