---
UID: NF:ntintsafe.RtlULongSub
title: RtlULongSub function
author: windows-driver-content
description: Subtracts one value of type ULONG from another.
old-location: kernel\rtlulongsub.htm
old-project: kernel
ms.assetid: 54776F17-C7EE-46DB-BA3F-2F545240FC61
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , L, R, RtlULongSub, RtlULongSub function [Kernel-Mode Driver Architecture], S, U, b, g, kernel.rtlulongsub, l, n, ntintsafe/RtlULongSub, o, t, u"
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
-	RtlULongSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongSub function


## -description


Subtracts one value of type <b>ULONG</b> from another.


## -syntax


````
NTSTATUS RtlULongSub(
  _In_  UINT8 ulMinuend,
  _In_  UINT8 ulSubtrahend,
  _Out_ UINT8 *pulResult
);
````


## -parameters




### -param ulMinuend [in]

The value from which <i>ulSubtrahend</i> is subtracted.


### -param ulSubtrahend [in]

The value to subtract from <i>ulMinuend</i>.


### -param pulResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



