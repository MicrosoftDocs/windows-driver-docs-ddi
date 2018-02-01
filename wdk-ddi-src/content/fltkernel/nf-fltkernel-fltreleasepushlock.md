---
UID: NF:fltkernel.FltReleasePushLock
title: FltReleasePushLock macro
author: windows-driver-content
description: The FltReleasePushLock routine releases a specified push lock owned by the current thread.
old-location: ifsk\fltreleasepushlock.htm
old-project: ifsk
ms.assetid: 34d1b945-329c-47ff-913d-5576eef665b8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fltkernel/FltReleasePushLock, FltReleasePushLock routine [Installable File System Drivers], ifsk.fltreleasepushlock, FltReleasePushLock, FltApiRef_p_to_z_31e736a4-7790-443f-a6bf-e43d3823ad27.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later.
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
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltReleasePushLock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltReleasePushLock macro


## -description


The <b>FltReleasePushLock</b> routine releases a specified push lock owned by the current thread.


## -syntax


````
VOID FltReleasePushLock(
  _Inout_ PEX_PUSH_LOCK PushLock
);
````


## -parameters




### -param Lock

TBD




#### - PushLock [in, out]

Opaque push lock pointer. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 


## -remarks


<b>FltReleasePushLock</b> releases a push lock that was previously acquired by calling <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md">FltAcquirePushLockExclusive</a> or <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>. 

Because <b>FltReleasePushLock</b> reenables normal kernel APC delivery, it is not necessary to call <a href="..\wdm\nf-wdm-keleavecriticalregion.md">KeLeaveCriticalRegion</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a> after calling <b>FltReleasePushLock</b>. 

For more information about push locks, see the reference entry for <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 

To acquire a push lock for exclusive access, call <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md">FltAcquirePushLockExclusive</a>. 

To acquire a push lock for shared access, call <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>. 

To initialize a push lock, call <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 

To delete a push lock, call <a href="..\fltkernel\nf-fltkernel-fltdeletepushlock.md">FltDeletePushLock</a>. 



## -see-also

<a href="..\wdm\nf-wdm-keleavecriticalregion.md">KeLeaveCriticalRegion</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletepushlock.md">FltDeletePushLock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a>

<a href="..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md">FltAcquirePushLockExclusive</a>

<a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>

<a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReleasePushLock routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

