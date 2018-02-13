---
UID: NF:ntintsafe.RtlShortToUChar
title: RtlShortToUChar function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type UCHAR.
old-location: kernel\rtlshorttouchar.htm
old-project: kernel
ms.assetid: 6DA0F939-F4B3-4E66-A90C-5112AE6FEC8D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlShortToUChar, RtlShortToUChar function [Kernel-Mode Driver Architecture], ntintsafe/RtlShortToUChar, kernel.rtlshorttouchar
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
-	RtlShortToUChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlShortToUChar function


## -description


Converts a value of type <b>SHORT</b> to a value of type <b>UCHAR</b>.


## -syntax


````
NTSTATUS RtlShortToUChar(
  _In_  SHORT sOperand,
  _Out_ UCHAR *pch
);
````


## -parameters




### -param sOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt16ToUChar
</li>
</ul>


