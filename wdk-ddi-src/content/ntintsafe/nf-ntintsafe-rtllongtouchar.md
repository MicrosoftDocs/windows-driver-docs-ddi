---
UID: NF:ntintsafe.RtlLongToUChar
title: RtlLongToUChar function
author: windows-driver-content
description: Converts a value of type LONG to a value of type UCHAR.
old-location: kernel\rtllongtouchar.htm
old-project: kernel
ms.assetid: 22440E1D-8DF5-4391-90F4-6080AAAC65D1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtllongtouchar, RtlLongToUChar, RtlLongToUChar function [Kernel-Mode Driver Architecture], ntintsafe/RtlLongToUChar
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
-	RtlLongToUChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToUChar function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>UCHAR</b>.


## -syntax


````
NTSTATUS RtlLongToUChar(
  _In_  LONG  lOperand,
  _Out_ UCHAR *pch
);
````


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


