---
UID: NF:fltkernel.FltAcquirePushLockExclusive
title: FltAcquirePushLockExclusive macro
author: windows-driver-content
description: The FltAcquirePushLockExclusive routine acquires the given push lock for exclusive access by the calling thread.
old-location: ifsk\fltacquirepushlockexclusive.htm
old-project: ifsk
ms.assetid: 98c916c4-49b0-47f5-acb1-ab1586d7a897
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltAcquirePushLockExclusive, FltAcquirePushLockExclusive routine [Installable File System Drivers], FltApiRef_a_to_d_0f7b3360-aea2-42a8-bcc0-299d1915e4e0.xml, fltkernel/FltAcquirePushLockExclusive, ifsk.fltacquirepushlockexclusive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAcquirePushLockExclusive
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAcquirePushLockExclusive macro


## -description


The <b>FltAcquirePushLockExclusive</b> routine acquires the given push lock for exclusive access by the calling thread.


## -syntax


````
VOID FltAcquirePushLockExclusive(
  _Inout_ PEX_PUSH_LOCK PushLock
);
````


## -parameters




### -param Lock

TBD






#### - PushLock [in, out]

Opaque push lock pointer. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 


## -remarks



This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

<b>FltAcquirePushLockExclusive</b> acquires the given push lock for exclusive access by the calling thread. 

Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 

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
Because <b>FltAcquirePushLockExclusive</b> disables normal kernel APC delivery, it is not necessary to call <a href="..\ntddk\nf-ntddk-keentercriticalregion.md">KeEnterCriticalRegion</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545900">FsRtlEnterFileSystem</a> before calling <b>FltAcquirePushLockExclusive</b>. 

To release the push lock after it is acquired, call <a href="..\fltkernel\nf-fltkernel-fltreleasepushlock.md">FltReleasePushLock</a>. Every call to <b>FltAcquirePushLockExclusive</b> must be matched by a subsequent call to <b>FltReleasePushLock</b>. 

To acquire a push lock for shared access, call <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>. 

To initialize a push lock, call <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 

To delete a push lock, call <a href="..\fltkernel\nf-fltkernel-fltdeletepushlock.md">FltDeletePushLock</a>. 




## -see-also

<a href="..\ntddk\nf-ntddk-keentercriticalregion.md">KeEnterCriticalRegion</a>



<a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasepushlock.md">FltReleasePushLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545900">FsRtlEnterFileSystem</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletepushlock.md">FltDeletePushLock</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAcquirePushLockExclusive routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

