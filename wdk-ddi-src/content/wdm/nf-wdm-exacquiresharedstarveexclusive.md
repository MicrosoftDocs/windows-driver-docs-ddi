---
UID: NF:wdm.ExAcquireSharedStarveExclusive
title: ExAcquireSharedStarveExclusive function
author: windows-driver-content
description: The ExAcquireSharedStarveExclusive routine acquires a given resource for shared access without waiting for any pending attempts to acquire exclusive access to the same resource.
old-location: kernel\exacquiresharedstarveexclusive.htm
old-project: kernel
ms.assetid: b148e684-18bd-4ab3-b772-6bc103b9f436
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: ExAcquireSharedStarveExclusive, ExAcquireSharedStarveExclusive routine [Kernel-Mode Driver Architecture], k102_b350fc88-cc76-4432-98e0-90e113e98007.xml, kernel.exacquiresharedstarveexclusive, wdm/ExAcquireSharedStarveExclusive
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
req.ddi-compliance: IrqlExApcLte3, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExAcquireSharedStarveExclusive
product: Windows
targetos: Windows
req.typenames: 
---

# ExAcquireSharedStarveExclusive function


## -description


The <b>ExAcquireSharedStarveExclusive</b> routine acquires a given resource for shared access without waiting for any pending attempts to acquire exclusive access to the same resource. 


## -parameters




### -param Resource [in, out]

A pointer to the resource to be acquired for shared access.


### -param Wait [in]

Specifies the routine's behavior whenever the resource cannot be acquired immediately. If <b>TRUE</b>, the caller is put into a wait state until the resource can be acquired. If <b>FALSE</b>, the routine immediately returns, regardless of whether the resource can be acquired.


## -returns



The caller can release the resource by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff545597">ExReleaseResourceLite</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a>.

<b>ExAcquireSharedStarveExclusive</b> returns <b>TRUE</b> if the requested access is granted. This routine returns <b>FALSE</b> if the input <i>Wait</i> is <b>FALSE</b> and shared access cannot be granted immediately.




## -remarks



Whether or when the caller is given shared access to the given resource depends on the following:

<ul>
<li>
If the resource is currently unowned, shared access is granted immediately to the current thread.

</li>
<li>
If the caller already has acquired the resource (for shared or exclusive access), the current thread is granted the same type of access recursively. Note that making this call does not convert a caller's exclusive access of a given resource to shared access. 

</li>
<li>
If the resource is currently owned as shared by another thread, shared access is granted to the caller immediately, even if another thread is waiting for exclusive access to that resource. 

</li>
<li>
If the resource is currently owned as exclusive by another thread, the caller either is put into a wait state (<i>Wait</i> set to <b>TRUE</b>) or <b>ExAcquireSharedStarveExclusive</b> returns <b>FALSE</b>.

</li>
</ul>
Callers of <b>ExAcquireSharedStarveExclusive</b> usually need quick access to a shared resource in order to save an exclusive accessor from doing redundant work. For example, a file system might call this routine to modify a cached resource, such as a BCB pinned in the cache, before the cache manager can acquire exclusive access to the resource and write the cache out to disk.

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552021">KeEnterCriticalRegion</a>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543219">Disabling APCs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544370">ExAcquireSharedWaitForExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544558">ExConvertExclusiveToSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544618">ExGetExclusiveWaiterCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545458">ExIsResourceAcquiredExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545477">ExIsResourceAcquiredSharedLite</a>
 

 

