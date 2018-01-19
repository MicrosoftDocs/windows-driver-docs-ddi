---
UID: NF:ntintsafe.RtlULongPtrToUInt8
title: RtlULongPtrToUInt8 function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type UINT8.
old-location: kernel\rtlulongptrtouint8.htm
old-project: kernel
ms.assetid: 7CAE67CD-44B3-48C0-AB9B-F67404D8FB7C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongPtrToUInt8
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
req.alt-api: RtlULongPtrToUInt8
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

# RtlULongPtrToUInt8 function



## -description
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>UINT8</b>.



## -syntax

````
NTSTATUS RtlULongPtrToUInt8(
  _In_  ULONG_PTR ulOperand,
  _Out_ UINT8     *pui8Result
);
````


## -parameters

### -param ulOperand [in]

The value to be converted.


### -param pui8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>