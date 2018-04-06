---
UID: NF:ntintsafe.RtlLongToULongLong
title: RtlLongToULongLong function
author: windows-driver-content
description: Converts a value of type LONG to a value of type ULONGLONG.
old-location: kernel\rtllongtoulonglong.htm
old-project: kernel
ms.assetid: 372B00C3-E5BD-4B2B-BB6B-F07878D661B4
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlLongToULongLong, RtlLongToULongLong function [Kernel-Mode Driver Architecture], kernel.rtllongtoulonglong, ntintsafe/RtlLongToULongLong
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
-	RtlLongToULongLong
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToULongLong function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>ULONGLONG</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pullResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToDWordLong
</li>
<li>RtlLongToULong64
</li>
<li>RtlLongToDWord64
</li>
<li>RtlLongToUInt64
</li>
</ul>


