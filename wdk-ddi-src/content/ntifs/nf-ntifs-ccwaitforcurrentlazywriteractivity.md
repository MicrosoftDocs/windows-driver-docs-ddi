---
UID: NF:ntifs.CcWaitForCurrentLazyWriterActivity
title: CcWaitForCurrentLazyWriterActivity function
author: windows-driver-content
description: The CcWaitForCurrentLazyWriterActivity routine puts the caller into a wait state until the current batch of lazy writer activity is completed.
old-location: ifsk\ccwaitforcurrentlazywriteractivity.htm
old-project: ifsk
ms.assetid: eda2198d-d9c9-498a-b94f-5ebdaae417be
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CcWaitForCurrentLazyWriterActivity, CcWaitForCurrentLazyWriterActivity routine [Installable File System Drivers], ccref_a216c467-24be-4ea5-9c53-71cf1fe1c47d.xml, ifsk.ccwaitforcurrentlazywriteractivity, ntifs/CcWaitForCurrentLazyWriterActivity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows 2000 and later.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcWaitForCurrentLazyWriterActivity
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcWaitForCurrentLazyWriterActivity function


## -description


The <b>CcWaitForCurrentLazyWriterActivity</b> routine puts the caller into a wait state until the current batch of lazy writer activity is completed.


## -parameters






## -returns



<b>CcWaitForCurrentLazyWriterActivity</b> can return one of the following NTSTATUS values: 




## -remarks



<b>CcWaitForCurrentLazyWriterActivity</b> puts the calling thread into a wait state until all work items currently in the lazy writer (read ahead or write behind) work queue have completed.

To prevent deadlock, the caller should release any currently held synchronization objects before calling <b>CcWaitForCurrentLazyWriterActivity</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539191">CcReadAhead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539203">CcSetAdditionalCacheAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539224">CcSetReadAheadGranularity</a>
 

 

