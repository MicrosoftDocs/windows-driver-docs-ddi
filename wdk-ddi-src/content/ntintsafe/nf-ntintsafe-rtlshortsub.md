---
UID: NF:ntintsafe.RtlShortSub
title: RtlShortSub function
author: windows-driver-content
description: Subtracts one value of type SHORT from another.
old-location: kernel\rtlshortsub.htm
old-project: kernel
ms.assetid: F94435C2-A2FC-44F4-8A21-E56CBEB8CC37
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlShortSub function [Kernel-Mode Driver Architecture], kernel.rtlshortsub, RtlShortSub, ntintsafe/RtlShortSub
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
-	RtlShortSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlShortSub function


## -description


Subtracts one value of type <b>SHORT</b> from another.


## -syntax


````
NTSTATUS RtlShortSub(
  _In_  SHORT sMinuend,
  _In_  SHORT sSubtrahend,
  _Out_ SHORT *psResult
);
````


## -parameters




### -param sMinuend [in]

The value from which <i>sSubtrahend</i> is subtracted.


### -param sSubtrahend [in]

The value to subtract from <i>sMinuend</i>.


### -param psResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt16Sub
</li>
</ul>


