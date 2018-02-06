---
UID: NF:ntintsafe.RtlULongLongAdd
title: RtlULongLongAdd function
author: windows-driver-content
description: Adds two values of type ULONGLONG.
old-location: kernel\rtlulonglongadd.htm
old-project: kernel
ms.assetid: AE58D20E-25A0-4D45-9E60-38EF2F1D1EF3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlulonglongadd, RtlULongLongAdd function [Kernel-Mode Driver Architecture], RtlULongLongAdd, ntintsafe/RtlULongLongAdd
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
-	RtlULongLongAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongLongAdd function


## -description


Adds two values of type <b>ULONGLONG</b>.


## -syntax


````
NTSTATUS RtlULongLongAdd(
  _In_  ULONGLONG ullAugend,
  _In_  ULONGLONG ullAddend,
  _Out_ ULONGLONG *pllResult
);
````


## -parameters




### -param ullAugend [in]

The first value in the equation.


### -param ullAddend [in]

The value to add to <i>ullAugend</i>.


### -param pullResult

TBD



#### - pllResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.


