---
UID: NF:ntintsafe.RtlLongToChar
title: RtlLongToChar function
author: windows-driver-content
description: Converts a value of type LONG to a value of type CHAR.
old-location: kernel\rtllongtochar.htm
old-project: kernel
ms.assetid: 4D326534-2DEB-419B-9E14-D88543071ECC
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongToChar function [Kernel-Mode Driver Architecture], RtlLongToChar, ntintsafe/RtlLongToChar, kernel.rtllongtochar
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
-	RtlLongToChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToChar function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>CHAR</b>.


## -syntax


````
NTSTATUS RtlLongToChar(
  _In_  LONG lOperand,
  _Out_ CHAR *pch
);
````


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


