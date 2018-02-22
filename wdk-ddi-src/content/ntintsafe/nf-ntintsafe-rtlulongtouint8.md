---
UID: NF:ntintsafe.RtlULongToUInt8
title: RtlULongToUInt8 function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type UINT8.
old-location: kernel\rtlulongtouint8.htm
old-project: kernel
ms.assetid: 56A205A5-A7A8-440D-B28B-B925E2107AEE
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlULongToUInt8, RtlULongToUInt8 function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongToUInt8, kernel.rtlulongtouint8
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
-	RtlULongToUInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongToUInt8 function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>UINT8</b>.


## -syntax


````
NTSTATUS RtlULongToUInt8(
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



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



