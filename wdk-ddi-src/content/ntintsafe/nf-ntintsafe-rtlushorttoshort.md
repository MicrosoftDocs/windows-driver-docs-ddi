---
UID: NF:ntintsafe.RtlUShortToShort
title: RtlUShortToShort function
author: windows-driver-content
description: Converts a value of type USHORT to a value of type SHORT.
old-location: kernel\rtlushorttoshort.htm
old-project: kernel
ms.assetid: 055B5605-2EBB-4B09-9C21-A8288D0DB3CD
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlushorttoshort, RtlUShortToShort, RtlUShortToShort function [Kernel-Mode Driver Architecture], ntintsafe/RtlUShortToShort
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
-	RtlUShortToShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUShortToShort function


## -description


Converts a value of type <b>USHORT</b> to a value of type <b>SHORT</b>.


## -syntax


````
NTSTATUS RtlUShortToShort(
  _In_  USHORT usOperand,
  _Out_ SHORT  *psResult
);
````


## -parameters




#### - usOperand [in]

The value to be converted.


#### - psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


