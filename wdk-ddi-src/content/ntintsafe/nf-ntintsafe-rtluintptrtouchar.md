---
UID: NF:ntintsafe.RtlUIntPtrToUChar
title: RtlUIntPtrToUChar function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type UCHAR.
old-location: kernel\rtluintptrtouchar.htm
old-project: kernel
ms.assetid: F5E4225F-4C66-44A8-9445-7D7DBAFA1DA4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtluintptrtouchar, ntintsafe/RtlUIntPtrToUChar, RtlUIntPtrToUChar, RtlUIntPtrToUChar function [Kernel-Mode Driver Architecture]
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
-	RtlUIntPtrToUChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlUIntPtrToUChar function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>UCHAR</b>.


## -syntax


````
NTSTATUS RtlUIntPtrToUChar(
  _In_  UINT_PTR uOperand,
  _Out_ UCHAR    *pch
);
````


## -parameters




### -param uOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlSizeTToUChar
</li>
</ul>

