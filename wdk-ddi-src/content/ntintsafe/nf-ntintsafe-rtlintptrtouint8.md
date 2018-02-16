---
UID: NF:ntintsafe.RtlIntPtrToUInt8
title: RtlIntPtrToUInt8 function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type UINT8.
old-location: kernel\rtlintptrtouint8.htm
old-project: kernel
ms.assetid: E51696DD-17CE-41F1-AD30-30AB93C81D05
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIntPtrToUInt8, kernel.rtlintptrtouint8, ntintsafe/RtlIntPtrToUInt8, RtlIntPtrToUInt8 function [Kernel-Mode Driver Architecture]
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
-	RtlIntPtrToUInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntPtrToUInt8 function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>UINT8</b>.


## -syntax


````
NTSTATUS RtlIntPtrToUInt8(
  _In_  INT_PTR iOperand,
  _Out_ UINT8   *pui8Result
);
````


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pui8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToByte
</li>
<li>RtlPtrdiffTToUInt8
</li>
<li>RtlPtrdiffTToByte
</li>
</ul>


