---
UID: NF:ntintsafe.RtlDWordPtrSub
title: RtlDWordPtrSub function
author: windows-driver-content
description: Subtracts one value of type DWORD_PTR from another.
old-location: kernel\rtldwordptrsub.htm
old-project: kernel
ms.assetid: B3268640-F256-4B64-AE95-8D30A6A7BF6C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlDWordPtrSub, RtlDWordPtrSub function [Kernel-Mode Driver Architecture], kernel.rtldwordptrsub, ntintsafe/RtlDWordPtrSub
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
-	RtlDWordPtrSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlDWordPtrSub function


## -description


Subtracts one value of type <b>DWORD_PTR</b> from another.


## -syntax


````
NTSTATUS RtlDWordPtrSub(
  _In_  DWORD_PTR dwMinuend,
  _In_  DWORD_PTR dwSubtrahend,
  _Out_ DWORD_PTR *pdwResult
);
````


## -parameters




### -param dwMinuend [in]

The value from which <i>dwSubtrahend</i> is subtracted.


### -param dwSubtrahend [in]

The value to subtract from <i>dwMinuend</i>.


### -param pdwResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



