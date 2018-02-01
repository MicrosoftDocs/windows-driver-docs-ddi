---
UID: NF:ntintsafe.RtlShortAdd
title: RtlShortAdd function
author: windows-driver-content
description: Adds two values of type SHORT.
old-location: kernel\rtlshortadd.htm
old-project: kernel
ms.assetid: 6CCBDECB-D52A-409D-91CA-6635E6D02545
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlShortAdd function [Kernel-Mode Driver Architecture], ntintsafe/RtlShortAdd, RtlShortAdd, kernel.rtlshortadd
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
-	RtlShortAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlShortAdd function


## -description


Adds two values of type <b>SHORT</b>.


## -syntax


````
NTSTATUS RtlShortAdd(
  _In_  SHORT sAugend,
  _In_  SHORT sAddend,
  _Out_ SHORT *psResult
);
````


## -parameters




### -param sAugend [in]

The first value in the equation.


### -param sAddend [in]

The value to add to <i>sAugend</i>.


### -param psResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlInt16Add
</li>
</ul>

