---
UID: NF:ntintsafe.RtlUInt8Add
title: RtlUInt8Add function
author: windows-driver-content
description: Adds two values of type UINT8.
old-location: kernel\rtluint8add.htm
old-project: kernel
ms.assetid: E93C8C7A-13E5-4089-931C-C56055FA3C90
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUInt8Add
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
req.alt-api: RtlUInt8Add
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

# RtlUInt8Add function



## -description
Adds two values of type <b>UINT8</b>.



## -syntax

````
NTSTATUS RtlUInt8Add(
  _In_  UINT8 u8Augend,
  _In_  UINT8 u8Addend,
  _Out_ UINT8 *pu8Result
);
````


## -parameters

### -param u8Augend [in]

The first value in the equation.


### -param u8Addend [in]

The value to add to <i>u8Augend</i>.


### -param pu8Result [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.</p>