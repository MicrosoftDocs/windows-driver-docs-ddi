---
UID: NF:ntintsafe.RtlULongAdd
title: RtlULongAdd function
author: windows-driver-content
description: Adds two values of type ULONG.
old-location: kernel\rtlulongadd.htm
old-project: kernel
ms.assetid: 03E5C0DB-E245-43E2-80C0-0C1D67673038
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongAdd
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
req.alt-api: RtlULongAdd
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

# RtlULongAdd function



## -description
Adds two values of type <b>ULONG</b>.



## -syntax

````
NTSTATUS RtlULongAdd(
  _In_  ULONG ulAugend,
  _In_  ULONG ulAddend,
  _Out_ ULONG *pulResult
);
````


## -parameters

### -param ulAugend [in]

The first value in the equation.


### -param ulAddend [in]

The value to add to <i>ulAugend</i>.


### -param pulResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.</p>