---
UID: NF:ntintsafe.RtlULongToUShort
title: RtlULongToUShort function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type USHORT.
old-location: kernel\rtlulongtoushort.htm
old-project: kernel
ms.assetid: 6D03736F-E972-4A76-935A-BB8682DC38B8
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlULongToUShort, RtlULongToUShort function [Kernel-Mode Driver Architecture], kernel.rtlulongtoushort, ntintsafe/RtlULongToUShort
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
-	RtlULongToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongToUShort function


## -description


Converts a value of type <b>ULONG</b> to a value of type <b>USHORT</b>.


## -syntax


````
NTSTATUS RtlULongToUShort(
  _In_  ULONG  ulOperand,
  _Out_ USHORT *pusResult
);
````


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



