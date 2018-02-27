---
UID: NF:ntintsafe.RtlIntToUChar
title: RtlIntToUChar function
author: windows-driver-content
description: Converts a value of type INT to a value of type UCHAR.
old-location: kernel\rtlinttouchar.htm
old-project: kernel
ms.assetid: A733140D-2F0D-4E5A-A3AD-C27756584200
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlIntToUChar, RtlIntToUChar function [Kernel-Mode Driver Architecture], kernel.rtlinttouchar, ntintsafe/RtlIntToUChar
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
-	RtlIntToUChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntToUChar function


## -description


Converts a value of type <b>INT</b> to a value of type <b>UCHAR</b>.


## -syntax


````
NTSTATUS RtlIntToUChar(
  _In_  INT   iOperand,
  _Out_ UCHAR *pch
);
````


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt32ToUChar
</li>
</ul>


