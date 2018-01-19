---
UID: NF:ntintsafe.RtlULongLongToLongLong
title: RtlULongLongToLongLong function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type LONGLONG.
old-location: kernel\rtlulonglongtolonglong.htm
old-project: kernel
ms.assetid: 7F91DDA1-AF01-4DA9-AB3B-AA5CA87C5FD6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongLongToLongLong
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
req.alt-api: RtlULongLongToLongLong
req.alt-loc: Ntintsafe.h
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
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongLongToLongLong function



## -description
Converts a value of type <b>ULONGLONG</b> to a value of type <b>LONGLONG</b>.



## -syntax

````
NTSTATUS RtlULongLongToLongLong(
  _In_  ULONGLONG ullOperand,
  _Out_ LONGLONG  *pllResult
);
````


## -parameters

### -param ullOperand [in]

The value to be converted.


### -param pllResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:</p>