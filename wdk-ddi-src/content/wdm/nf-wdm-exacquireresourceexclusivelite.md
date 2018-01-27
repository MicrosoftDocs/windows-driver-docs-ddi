---
UID: NF:wdm.ExAcquireResourceExclusiveLite
title: ExAcquireResourceExclusiveLite function
author: windows-driver-content
description: The ExAcquireResourceExclusiveLite routine acquires the given resource for exclusive access by the calling thread.
old-location: kernel\exacquireresourceexclusivelite.htm
old-project: kernel
ms.assetid: c7f8a6c5-15d5-4a24-a351-4fa5d6c72fbd
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExAcquireResourceExclusiveLite routine [Kernel-Mode Driver Architecture], ExAcquireResourceExclusiveLite, k102_894dbc3c-af92-4916-8205-539062946dbe.xml, wdm/ExAcquireResourceExclusiveLite, kernel.exacquireresourceexclusivelite
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
req.ddi-compliance: ExclusiveResourceAccess, IrqlExApcLte3, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	ExAcquireResourceExclusiveLite
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAcquireResourceExclusiveLite function


## -description


The <b>ExAcquireResourceExclusiveLite</b> routine acquires the given resource for exclusive access by the calling thread.


## -syntax


````
BOOLEAN ExAcquireResourceExclusiveLite(
  _Inout_ PERESOURCE Resource,
  _In_    BOOLEAN    Wait
);
````


## -parameters




### -param Resource [in, out]

A pointer to the resource to acquire.


### -param Wait [in]

Specifies the routine's behavior whenever the resource cannot be acquired immediately. If <b>TRUE</b>, the caller is put into a wait state until the resource can be acquired. If <b>FALSE</b>, the routine immediately returns, regardless of whether the resource can be acquired. 


## -returns


<b>ExAcquireResourceExclusiveLite</b> returns <b>TRUE</b> if the resource is acquired. This routine returns <b>FALSE</b> if the input <i>Wait</i> is <b>FALSE</b> and exclusive access cannot be granted immediately.



## -remarks


The following list describes whether and when a caller is given exclusive access to a given resource:
<ul>
<li>
If the resource is currently not owned, exclusive access is granted immediately to the current thread.

</li>
<li>
If the caller already had acquired the resource for exclusive access, the current thread is granted the same type of access recursively.

</li>
<li>
If the caller has shared access to the resource, the caller must release the lock before it attempts to reacquire it exclusively.

</li>
<li>
If the resource is currently owned as exclusive by another thread, or if the caller only has shared access to the resource, the current thread is put into a wait state until the resource can be acquired.

</li>
</ul><div class="alert"><b>Note</b>    If two threads each hold a shared lock on the same resource and both attempt to acquire the lock exclusively without releasing their shared lock, they will deadlock. This means that each thread will wait for the other to release its shared hold on the lock, and neither will release its shared hold until the other does.</div><div> </div>The caller can release the resource by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff545597">ExReleaseResourceLite</a> or <a href="..\wdm\nf-wdm-exreleaseresourceforthreadlite.md">ExReleaseResourceForThreadLite</a>.

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling <a href="..\wdm\nf-wdm-keentercriticalregion.md">KeEnterCriticalRegion</a>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <a href="..\wdm\nf-wdm-keleavecriticalregion.md">KeLeaveCriticalRegion</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543219">Disabling APCs</a>.



## -see-also

<a href="..\wdm\nf-wdm-exreinitializeresourcelite.md">ExReinitializeResourceLite</a>

<a href="..\wdm\nf-wdm-exisresourceacquiredexclusivelite.md">ExIsResourceAcquiredExclusiveLite</a>

<a href="..\wdm\nf-wdm-exacquireresourcesharedlite.md">ExAcquireResourceSharedLite</a>

<a href="..\wdm\nf-wdm-keentercriticalregion.md">KeEnterCriticalRegion</a>

<a href="..\wdm\nf-wdm-exgetsharedwaitercount.md">ExGetSharedWaiterCount</a>

<a href="..\wdm\nf-wdm-exinitializeresourcelite.md">ExInitializeResourceLite</a>

<a href="..\wdm\nf-wdm-exreleaseresourceforthreadlite.md">ExReleaseResourceForThreadLite</a>

<a href="..\wdm\nf-wdm-exgetexclusivewaitercount.md">ExGetExclusiveWaiterCount</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAcquireResourceExclusiveLite routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

