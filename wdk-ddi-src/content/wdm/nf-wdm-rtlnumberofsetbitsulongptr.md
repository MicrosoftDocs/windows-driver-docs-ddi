---
UID: NF:wdm.RtlNumberOfSetBitsUlongPtr
title: RtlNumberOfSetBitsUlongPtr function
author: windows-driver-content
description: The RtlNumberOfSetBitsUlongPtr routine returns the number of bits in the specified ULONG_PTR integer value that are set to one.
old-location: kernel\rtlnumberofsetbitsulongptr.htm
old-project: kernel
ms.assetid: CD619018-7E6D-4B45-93C3-AD89FDFEB1E9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlNumberOfSetBitsUlongPtr, RtlNumberOfSetBitsUlongPtr routine [Kernel-Mode Driver Architecture], kernel.rtlnumberofsetbitsulongptr, wdm/RtlNumberOfSetBitsUlongPtr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any IRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlNumberOfSetBitsUlongPtr
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlNumberOfSetBitsUlongPtr function


## -description


The <b>RtlNumberOfSetBitsUlongPtr</b> routine returns the number of bits in the specified ULONG_PTR integer value that are set to one.


## -syntax


````
ULONG RtlNumberOfSetBitsUlongPtr(
  _In_ ULONG_PTR Target
);
````


## -parameters




### -param Target [in]

A ULONG_PTR integer value.


## -returns



<b>RtlNumberOfSetBitsUlongPtr</b> returns a count of the bits in the <i>Target</i> parameter that are set to one.



