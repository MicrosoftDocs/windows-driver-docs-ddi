---
UID: NF:ntintsafe.RtlUIntPtrToUInt16
title: RtlUIntPtrToUInt16 function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type UINT16.
old-location: kernel\rtluintptrtouint16.htm
old-project: kernel
ms.assetid: 405FB676-64FD-43DE-BCD9-233C8B43D851
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 1, 6, I, P, R, RtlUIntPtrToUInt16, RtlUIntPtrToUInt16 function [Kernel-Mode Driver Architecture], T, U, kernel.rtluintptrtouint16, l, n, ntintsafe/RtlUIntPtrToUInt16, o, r, t"
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
-	RtlUIntPtrToUInt16
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntPtrToUInt16 function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>UINT16</b>.


## -syntax


````
NTSTATUS RtlUIntPtrToUInt16(
  _In_  UINT_PTR uOperand,
  _Out_ UINT16   *pu16Result
);
````


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pu16Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



