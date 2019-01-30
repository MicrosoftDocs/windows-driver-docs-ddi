---
UID: NF:wdm.KeFlushQueuedDpcs
title: KeFlushQueuedDpcs function (wdm.h)
description: The KeFlushQueuedDpcs routine returns after all queued DPCs on all processors have executed.
old-location: kernel\keflushqueueddpcs.htm
tech.root: kernel
ms.assetid: e5237e44-fff1-4928-9029-f1d1691ef2e3
ms.date: 04/30/2018
ms.keywords: KeFlushQueuedDpcs, KeFlushQueuedDpcs routine [Kernel-Mode Driver Architecture], k105_6aaf8f1a-0fa7-422a-b390-ba0f92558a65.xml, kernel.keflushqueueddpcs, wdm/KeFlushQueuedDpcs
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP with SP2 and Windows Server 2003.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeFlushQueuedDpcs
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeFlushQueuedDpcs function


## -description


The <b>KeFlushQueuedDpcs</b> routine returns after all queued DPCs on all processors have executed.


## -parameters






## -returns



None




## -remarks



Drivers can use this routine to wait until all currently-queued DPCs are run. Note that <b>KeFlushQueuedDpcs</b> can take a long time to return, so drivers should not use it along any critical code paths.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549307">IoInitializeDpcRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549657">IoRequestDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552130">KeInitializeDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a>
 

 

