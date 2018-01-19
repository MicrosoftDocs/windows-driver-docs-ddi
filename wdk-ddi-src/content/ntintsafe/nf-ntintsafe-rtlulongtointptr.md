---
UID: NF:ntintsafe.RtlULongToIntPtr
title: RtlULongToIntPtr function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type INT_PTR.
old-location: kernel\rtlulongtointptr.htm
old-project: kernel
ms.assetid: EEAA1C05-BB93-4D8A-9AD6-6F109BBE4FE0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongToIntPtr
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
req.alt-api: RtlULongToIntPtr
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

# RtlULongToIntPtr function



## -description
Converts a value of type <b>ULONG</b> to a value of type <b>INT_PTR</b>.



## -syntax

````
NTSTATUS RtlULongToIntPtr(
  _In_  ULONG   ulOperand,
  _Out_ INT_PTR *piResult
);
````


## -parameters

### -param ulOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>