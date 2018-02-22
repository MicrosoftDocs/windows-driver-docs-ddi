---
UID: NF:ntintsafe.RtlLongPtrToUInt8
title: RtlLongPtrToUInt8 function
author: windows-driver-content
description: Converts a value of type LONG_PTR to a value of type UINT8.
old-location: kernel\rtllongptrtouint8.htm
old-project: kernel
ms.assetid: 1E7BB805-1A91-4DA6-A7E9-E60DD8D4AAF3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlLongPtrToUInt8 function [Kernel-Mode Driver Architecture], ntintsafe/RtlLongPtrToUInt8, RtlLongPtrToUInt8, kernel.rtllongptrtouint8
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
-	RtlLongPtrToUInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongPtrToUInt8 function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>UINT8</b>.


## -syntax


````
NTSTATUS RtlLongPtrToUInt8(
  _In_  LONG_PTR lOperand,
  _Out_ UINT8    *pui8Result
);
````


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pui8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongPtrToByte
</li>
<li>RtlSSIZETToUInt8
</li>
<li>RtlSSIZETToByte
</li>
</ul>


