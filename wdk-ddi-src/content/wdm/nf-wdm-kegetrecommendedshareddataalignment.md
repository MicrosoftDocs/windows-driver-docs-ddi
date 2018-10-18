---
UID: NF:wdm.KeGetRecommendedSharedDataAlignment
title: KeGetRecommendedSharedDataAlignment function
author: windows-driver-content
description: The KeGetRecommendedSharedDataAlignment routine returns the preferred alignment for memory structures that can be accessed by more than one processor.
old-location: kernel\kegetrecommendedshareddataalignment.htm
tech.root: kernel
ms.assetid: 2faf5e30-bfbb-4b23-9cb9-bf9dd81a56c2
ms.date: 4/30/2018
ms.keywords: KeGetRecommendedSharedDataAlignment, KeGetRecommendedSharedDataAlignment routine [Kernel-Mode Driver Architecture], k105_537a55c5-9c7e-49cb-8a27-de61e92b78e2.xml, kernel.kegetrecommendedshareddataalignment, wdm/KeGetRecommendedSharedDataAlignment
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeGetRecommendedSharedDataAlignment
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeGetRecommendedSharedDataAlignment function


## -description


The <b>KeGetRecommendedSharedDataAlignment</b> routine returns the preferred alignment for memory structures that can be accessed by more than one processor.


## -parameters






## -returns



<b>KeGetRecommendedSharedDataAlignment</b> returns the preferred alignment, in bytes, for memory structures that can be shared by more than one processor.




## -remarks



Use <b>KeGetRecommendedSharedDataAlignment</b> to determine the best alignment for data structures that will be shared between processors. The value returned minimizes cache effects that negatively impact performance on multiprocessor systems.



