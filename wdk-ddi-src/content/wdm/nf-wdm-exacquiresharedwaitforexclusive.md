---
UID: NF:wdm.ExAcquireSharedWaitForExclusive
title: ExAcquireSharedWaitForExclusive function
author: windows-driver-content
description: The ExAcquireSharedWaitForExclusive routine acquires the given resource for shared access if shared access can be granted and there are no exclusive waiters.
old-location: kernel\exacquiresharedwaitforexclusive.htm
old-project: kernel
ms.assetid: 745b014d-7ab4-4e07-a24c-7a74949a9d7b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExAcquireSharedWaitForExclusive
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
req.alt-api: ExAcquireSharedWaitForExclusive
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlExApcLte3, WithinCriticalRegion, HwStorPortProhibitedDDIs, SpNoWait, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAcquireSharedWaitForExclusive function



## -description
The <b>ExAcquireSharedWaitForExclusive</b> routine acquires the given resource for shared access if shared access can be granted and there are no exclusive waiters. 



## -syntax

````
BOOLEAN ExAcquireSharedWaitForExclusive(
  _Inout_ PERESOURCE Resource,
  _In_    BOOLEAN    Wait
);
````


## -parameters

### -param Resource [in, out]

A pointer to the resource to be acquired for shared access.


### -param Wait [in]

Specifies the routine's behavior whenever the resource cannot be acquired immediately. If <b>TRUE</b>, the caller is put into a wait state until the resource can be acquired. If <b>FALSE</b>, the routine immediately returns, regardless of whether the resource can be acquired. 


## -returns
<b>ExAcquireSharedWaitForExclusive</b> returns <b>TRUE</b> if the requested access is granted or an exclusive owner releases the resource. This routine returns <b>FALSE</b> if the input <i>Wait</i> is <b>FALSE</b> and shared access cannot be granted immediately. 


## -remarks
Most drivers should use <a href="..\wdm\nf-wdm-exacquireresourcesharedlite.md">ExAcquireResourceSharedLite</a> instead of <b>ExAcquireSharedWaitForExclusive</b>.

The caller can release the resource by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff545597">ExReleaseResourceLite</a> or <a href="..\wdm\nf-wdm-exreleaseresourceforthreadlite.md">ExReleaseResourceForThreadLite</a>.

If shared access cannot be granted immediately, the caller can wait for other threads to acquire and release exclusive ownership of the resource.

Whether or when the caller is given shared access to the given resource depends on the following:

If the resource is currently unowned, shared access is granted immediately to the current thread.

If the caller already has exclusive access to the resource, the current thread is granted the same type of access recursively. 

If the resource is currently owned as shared and there are no pending attempts to acquire exclusive access, shared access is granted to the caller immediately. 

If the resource is currently owned as shared but there is a pending attempt to acquire exclusive access, the caller either is put into a wait state (<i>Wait</i> set to <b>TRUE</b>) or <b>ExAcquireSharedWaitForExclusive</b> returns <b>FALSE</b>.

When the current thread waits to acquire the resource until after a pending exclusive ownership has been released, <b>ExAcquireSharedWaitForExclusive</b> returns <b>TRUE</b> when the current thread is granted shared access to the resource and resumes execution. 

The behavior of <b>ExAcquireSharedWaitForExclusive</b> is identical to that of <a href="..\wdm\nf-wdm-exacquireresourcesharedlite.md">ExAcquireResourceSharedLite</a> unless the calling thread already owns the resource as shared and there are exclusive waiters. In that case, <b>ExAcquireSharedWaitForExclusive</b> allows the exclusive waiters to acquire exclusive ownership of the resource.

If the caller specifies <b>TRUE</b> for the <i>Wait</i> parameter, the caller blocks until another thread frees the resource on behalf of the caller, using <a href="https://msdn.microsoft.com/library/windows/hardware/ff545577">ExReleaseResourceForThread</a>. Driver writers must be careful to ensure that another thread actually releases the resource; otherwise the caller is deadlocked. <b>ExAcquireResourceSharedLite</b> does not have this property, so drivers should use that routine unless they require the particular behavior of <b>ExAcquireSharedWaitForExclusive</b>.

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling <a href="..\ntddk\nf-ntddk-keentercriticalregion.md">KeEnterCriticalRegion</a>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <a href="..\ntddk\nf-ntddk-keleavecriticalregion.md">KeLeaveCriticalRegion</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543219">Disabling APCs</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exacquireresourcesharedlite.md">ExAcquireResourceSharedLite</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exacquiresharedstarveexclusive.md">ExAcquireSharedStarveExclusive</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exconvertexclusivetosharedlite.md">ExConvertExclusiveToSharedLite</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exgetexclusivewaitercount.md">ExGetExclusiveWaiterCount</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exisresourceacquiredexclusivelite.md">ExIsResourceAcquiredExclusiveLite</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exisresourceacquiredsharedlite.md">ExIsResourceAcquiredSharedLite</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545577">ExReleaseResourceForThread</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAcquireSharedWaitForExclusive routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

