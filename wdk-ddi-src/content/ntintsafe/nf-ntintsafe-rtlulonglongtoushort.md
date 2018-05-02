---
UID: NF:ntintsafe.RtlULongLongToUShort
title: RtlULongLongToUShort function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type USHORT.
old-location: kernel\rtlulonglongtoushort.htm
old-project: kernel
ms.assetid: 209EDB33-34DB-429F-BDEB-B84960E6F20F
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlULongLongToUShort, RtlULongLongToUShort function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtoushort, ntintsafe/RtlULongLongToUShort
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
-	RtlULongLongToUShort
product: Windows
targetos: Windows
req.typenames: 
---

# RtlULongLongToUShort function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>USHORT</b>.


## -parameters




### -param ullOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUInt64ToDWord
</li>
<li>RtlULongLongToUInt16
</li>
<li>RtlULongLongToWord
</li>
<li>RtlDWordLongToUShort
</li>
<li>RtlDWordLongToUInt16
</li>
<li>RtlDWordLongToWord
</li>
<li>RtlULong64ToUShort
</li>
<li>RtlULong64ToUInt16
</li>
<li>RtlULong64ToWord
</li>
<li>RtlDWord64ToUShort
</li>
<li>RtlDWord64ToUInt16
</li>
<li>RtlDWord64ToWord
</li>
<li>RtlUInt64ToUShort
</li>
<li>RtlUInt64ToUInt16
</li>
<li>RtlUInt64ToWord
</li>
</ul>


