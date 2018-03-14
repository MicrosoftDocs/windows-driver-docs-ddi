---
UID: NF:ntintsafe.RtlLongToUInt8
title: RtlLongToUInt8 function
author: windows-driver-content
description: Converts a value of type LONG to a value of type UINT8.
old-location: kernel\rtllongtouint8.htm
old-project: kernel
ms.assetid: 3C2221F8-DD75-4FB7-A28D-B636D2D2394D
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlLongToUInt8, RtlLongToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtllongtouint8, ntintsafe/RtlLongToUInt8
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlLongToUInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToUInt8 function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>UINT8</b>.


## -syntax


````
NTSTATUS RtlLongToUInt8(
  _In_  ULONG  ulOperand,
  _Out_ USHORT *pusResult
);
````


## -parameters




### -param lOperand

TBD


### -param pui8Result

TBD




#### - pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


#### - ulOperand [in]

The value to be converted.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToByte
</li>
</ul>


