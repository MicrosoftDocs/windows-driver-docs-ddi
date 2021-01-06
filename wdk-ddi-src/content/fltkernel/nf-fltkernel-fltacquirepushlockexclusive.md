---
UID: NF:fltkernel.FltAcquirePushLockExclusive
title: FltAcquirePushLockExclusive macro (fltkernel.h)
description: The FltAcquirePushLockExclusive routine acquires the given push lock for exclusive access by the calling thread.
old-location: ifsk\fltacquirepushlockexclusive.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltAcquirePushLockExclusive macro"]
ms.keywords: FltAcquirePushLockExclusive, FltAcquirePushLockExclusive routine [Installable File System Drivers], FltApiRef_a_to_d_0f7b3360-aea2-42a8-bcc0-299d1915e4e0.xml, fltkernel/FltAcquirePushLockExclusive, ifsk.fltacquirepushlockexclusive
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltAcquirePushLockExclusive
 - fltkernel/FltAcquirePushLockExclusive
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltAcquirePushLockExclusive
---

# FltAcquirePushLockExclusive macro


## -description

The <b>FltAcquirePushLockExclusive</b> routine acquires the given push lock for exclusive access by the calling thread.

## -parameters

### -param PushLock 

[in, out]
Opaque push lock pointer of type **PEX_PUSH_LOCK**. This pointer must have been initialized by a previous call to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>.

## -remarks

This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

<b>FltAcquirePushLockExclusive</b> acquires the given push lock for exclusive access by the calling thread. 

Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>. 

Unlike ERESOURCE structures, push locks cannot be acquired recursively. If the caller already has acquired the push lock for exclusive or shared access, the thread will hang. 

When the caller will be given exclusive access to the given push lock depends on the following:

<ul>
<li>
If the push lock is currently unowned, exclusive access is granted immediately to the current thread.

</li>
<li>
If the push lock has already been acquired for exclusive or shared access by another thread, the current thread is put into a wait state until the push lock can be acquired. 

</li>
</ul>
Because <b>FltAcquirePushLockExclusive</b> disables normal kernel APC delivery, it is not necessary to call <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a> or <a href="/windows-hardware/drivers/ifs/fsrtlenterfilesystem">FsRtlEnterFileSystem</a> before calling <b>FltAcquirePushLockExclusive</b>. 

To release the push lock after it is acquired, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasepushlock">FltReleasePushLock</a>. Every call to <b>FltAcquirePushLockExclusive</b> must be matched by a subsequent call to <b>FltReleasePushLock</b>. 

To acquire a push lock for shared access, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockshared">FltAcquirePushLockShared</a>. 

To initialize a push lock, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>. 

To delete a push lock, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletepushlock">FltDeletePushLock</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockshared">FltAcquirePushLockShared</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletepushlock">FltDeletePushLock</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasepushlock">FltReleasePushLock</a>



<a href="/windows-hardware/drivers/ifs/fsrtlenterfilesystem">FsRtlEnterFileSystem</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a>
