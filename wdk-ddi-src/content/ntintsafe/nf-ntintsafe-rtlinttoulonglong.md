---
UID: NF:ntintsafe.RtlIntToULongLong
title: RtlIntToULongLong function
author: windows-driver-content
description: Converts a value of type INT to a value of type ULONGLONG.
old-location: kernel\rtlinttoulonglong.htm
old-project: kernel
ms.assetid: AED881EC-D417-49F5-B0B7-497FDF450968
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlIntToULongLong, RtlIntToULongLong function [Kernel-Mode Driver Architecture], kernel.rtlinttoulonglong, ntintsafe/RtlIntToULongLong
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
-	RtlIntToULongLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlIntToULongLong function


## -description


Converts a value of type <b>INT</b> to a value of type <b>ULONGLONG</b>.


## -syntax


````
NTSTATUS RtlIntToULongLong(
  _In_  INT       iOperand,
  _Out_ ULONGLONG *pullResult
);
````


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pullResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntToDWordLong
</li>
<li>RtlIntToULong64
</li>
<li>RtlIntToDWord64
</li>
<li>RtlIntToUInt64
</li>
<li>RtlInt32ToULongLong
</li>
<li>RtlInt32ToDWordLong
</li>
<li>RtlInt32ToULong64
</li>
<li>RtlInt32ToDWord64
</li>
<li>RtlInt32ToUInt64
</li>
<li>RtlIntToUIntPtr</li>
<li>RtlIntToSizeT
</li>
<li>RtlInt32ToUIntPtr
</li>
<li>RtlInt32ToSizeT
</li>
<li>RtlIntToUIntPtr
</li>
<li>RtlIntToULongPtr
</li>
<li>RtlIntToDWordPtr
</li>
<li>RtlIntToSIZET
</li>
<li>RtlInt32ToULongPtr
</li>
<li>RtlInt32ToDWordPtr
</li>
<li>RtlInt32ToSIZET
</li>
<li>RtlIntToULongPtr
</li>
</ul>


