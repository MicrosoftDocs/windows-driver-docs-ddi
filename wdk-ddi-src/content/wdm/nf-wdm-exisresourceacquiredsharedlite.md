---
UID: NF:wdm.ExIsResourceAcquiredSharedLite
title: ExIsResourceAcquiredSharedLite function
author: windows-driver-content
description: The ExIsResourceAcquiredSharedLite routine returns whether the current thread has access (either shared or exclusive) to a given resource.
old-location: kernel\exisresourceacquiredsharedlite.htm
old-project: kernel
ms.assetid: e87a4078-dbd4-4df2-bbfb-efbf76fc6279
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExIsResourceAcquiredLite, ExIsResourceAcquiredSharedLite, ExIsResourceAcquiredSharedLite routine [Kernel-Mode Driver Architecture], k102_e1ae158d-fd02-4962-813f-7bd87943f033.xml, kernel.exisresourceacquiredsharedlite, wdm/ExIsResourceAcquiredSharedLite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExIsResourceAcquiredSharedLite
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExIsResourceAcquiredSharedLite function


## -description


The <b>ExIsResourceAcquiredSharedLite</b> routine returns whether the current thread has access (either shared or exclusive) to a given resource.


## -parameters




### -param Resource [in]

A pointer to the resource to be queried.


## -returns



<b>ExIsResourceAcquiredSharedLite</b> returns the number of times the caller has acquired the given resource for shared or exclusive access.




## -remarks



The system considers exclusive access to be a subset of shared access. Therefore, a thread that has exclusive access to a resource also has shared access to the resource.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544367">ExAcquireSharedStarveExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544370">ExAcquireSharedWaitForExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545458">ExIsResourceAcquiredExclusiveLite</a>
 

 

