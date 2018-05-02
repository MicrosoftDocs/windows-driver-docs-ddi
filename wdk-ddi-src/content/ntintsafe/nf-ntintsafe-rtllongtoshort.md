---
UID: NF:ntintsafe.RtlLongToShort
title: RtlLongToShort function
author: windows-driver-content
description: Converts a value of type LONG to a value of type SHORT.
old-location: kernel\rtllongtoshort.htm
old-project: kernel
ms.assetid: FDFEADE6-CD33-4C04-972B-3E31C43E730A
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlLongToShort, RtlLongToShort function [Kernel-Mode Driver Architecture], kernel.rtllongtoshort, ntintsafe/RtlLongToShort
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
-	RtlLongToShort
product: Windows
targetos: Windows
req.typenames: 
---

# RtlLongToShort function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>SHORT</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToInt16
</li>
</ul>


