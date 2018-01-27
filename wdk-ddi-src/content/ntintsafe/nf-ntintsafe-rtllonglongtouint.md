---
UID: NF:ntintsafe.RtlLongLongToUInt
title: RtlLongLongToUInt function
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type UINT.
old-location: kernel\rtllonglongtouint.htm
old-project: kernel
ms.assetid: 81B87CA6-01D8-4D54-87A6-6311260C06CB
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlLongLongToUInt, RtlLongLongToUInt function [Kernel-Mode Driver Architecture], kernel.rtllonglongtouint, RtlLongLongToUInt
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
-	RtlLongLongToUInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongLongToUInt function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>UINT</b>.


## -syntax


````
NTSTATUS RtlLongLongToUInt(
  _In_  LONGLONG llOperand,
  _Out_ UINT     *puResult
);
````


## -parameters




### -param llOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlIntPtrToUInt
</li>
<li>RtlLongPtrToUInt
</li>
<li>RtlLongLongToUInt32
</li>
<li>RtlLongLongToUIntPtr
</li>
<li>RtlLong64ToUInt
</li>
<li>RtlLong64ToUInt32
</li>
<li>RtlInt64ToUInt
</li>
<li>RtlInt64ToUInt32
</li>
<li>RtlLongLongToSizeT
</li>
<li>RtlLong64ToUIntPtr
</li>
<li>RtlLong64ToSizeT
</li>
<li>RtlInt64ToUIntPtr
</li>
<li>RtlInt64ToSizeT
</li>
</ul>

