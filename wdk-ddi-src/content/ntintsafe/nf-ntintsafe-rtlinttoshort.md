---
UID: NF:ntintsafe.RtlIntToShort
title: RtlIntToShort function
author: windows-driver-content
description: Converts a value of type INT to a value of type SHORT.
old-location: kernel\rtlinttoshort.htm
old-project: kernel
ms.assetid: E8E05F9B-2F83-4537-979E-024E8412D733
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIntToShort
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
req.alt-api: RtlIntToShort
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

# RtlIntToShort function



## -description
Converts a value of type <b>INT</b> to a value of type <b>SHORT</b>.



## -syntax

````
NTSTATUS RtlIntToShort(
  _In_  INT   iOperand,
  _Out_ SHORT *psResult
);
````


## -parameters

### -param iOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:</p>