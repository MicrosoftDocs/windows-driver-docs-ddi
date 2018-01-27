---
UID: NF:ntintsafe.RtlUShortAdd
title: RtlUShortAdd function
author: windows-driver-content
description: Adds two values of type USHORT.
old-location: kernel\rtlushortadd.htm
old-project: kernel
ms.assetid: 07167C7E-E8EB-41E3-B2E3-7B9E9CCC5465
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlUShortAdd, kernel.rtlushortadd, RtlUShortAdd function [Kernel-Mode Driver Architecture], RtlUShortAdd
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
-	RtlUShortAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUShortAdd function


## -description


Adds two values of type <b>USHORT</b>.


## -syntax


````
NTSTATUS RtlUShortAdd(
  _In_  USHORT usAugend,
  _In_  USHORT usAddend,
  _Out_ USHORT *pusResult
);
````


## -parameters




### -param usAugend [in]

The first value in the equation.


### -param usAddend [in]

The value to add to <i>usAugend</i>.


### -param pusResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.


