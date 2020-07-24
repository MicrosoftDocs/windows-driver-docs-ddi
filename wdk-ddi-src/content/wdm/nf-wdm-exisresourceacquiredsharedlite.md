---
UID: NF:wdm.ExIsResourceAcquiredSharedLite
title: ExIsResourceAcquiredSharedLite function (wdm.h)
description: The ExIsResourceAcquiredSharedLite routine returns whether the current thread has access (either shared or exclusive) to a given resource.
old-location: kernel\exisresourceacquiredsharedlite.htm
tech.root: kernel
ms.assetid: e87a4078-dbd4-4df2-bbfb-efbf76fc6279
ms.date: 04/30/2018
keywords: ["ExIsResourceAcquiredSharedLite function"]
ms.keywords: ExIsResourceAcquiredLite, ExIsResourceAcquiredSharedLite, ExIsResourceAcquiredSharedLite routine [Kernel-Mode Driver Architecture], k102_e1ae158d-fd02-4962-813f-7bd87943f033.xml, kernel.exisresourceacquiredsharedlite, wdm/ExIsResourceAcquiredSharedLite
f1_keywords:
 - "wdm/ExIsResourceAcquiredSharedLite"
 - "ExIsResourceAcquiredSharedLite"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExIsResourceAcquiredSharedLite
targetos: Windows
req.typenames: 
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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a>
 

 

