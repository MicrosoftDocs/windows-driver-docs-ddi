---
UID: NF:ntintsafe.RtlULongToUInt
title: RtlULongToUInt function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type UINT.
old-location: kernel\rtlulongtouint.htm
old-project: kernel
ms.assetid: 110A77D5-48FD-4C10-BE2B-8BA9510F6334
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongToUInt, ntintsafe/RtlULongToUInt, RtlULongToUInt function [Kernel-Mode Driver Architecture], kernel.rtlulongtouint
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
-	RtlULongToUInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongToUInt function


## -description


Converts a value of type <b>ULONG</b> to a value of type <b>UINT</b>.


## -syntax


````
NTSTATUS RtlULongToUInt(
  _In_  ULONG ulOperand,
  _Out_ UINT  *puResult
);
````


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


