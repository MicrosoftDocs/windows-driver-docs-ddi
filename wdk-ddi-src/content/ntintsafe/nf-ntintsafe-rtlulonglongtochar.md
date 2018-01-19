---
UID: NF:ntintsafe.RtlULongLongToChar
title: RtlULongLongToChar function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type CHAR.
old-location: kernel\rtlulonglongtochar.htm
old-project: kernel
ms.assetid: 8C6356A2-9E4A-4654-9FB3-EC11894A24AB
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongLongToChar
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
req.alt-api: RtlULongLongToChar
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

# RtlULongLongToChar function



## -description
Converts a value of type <b>ULONGLONG</b> to a value of type <b>CHAR</b>.



## -syntax

````
NTSTATUS RtlULongLongToChar(
  _In_  ULONGLONG ullOperand,
  _Out_ CHAR      *pch
);
````


## -parameters

### -param ullOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>