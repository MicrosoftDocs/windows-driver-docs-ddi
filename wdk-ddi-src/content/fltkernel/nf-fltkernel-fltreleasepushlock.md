---
UID: NF:fltkernel.FltReleasePushLock
title: FltReleasePushLock macro
description: The FltReleasePushLock routine releases a specified push lock owned by the current thread.
old-location: ifsk\fltreleasepushlock.htm
tech.root: ifsk
ms.assetid: 34d1b945-329c-47ff-913d-5576eef665b8
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_31e736a4-7790-443f-a6bf-e43d3823ad27.xml, FltReleasePushLock, FltReleasePushLock routine [Installable File System Drivers], fltkernel/FltReleasePushLock, ifsk.fltreleasepushlock
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltReleasePushLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltReleasePushLock macro


## -description


The <b>FltReleasePushLock</b> routine releases a specified push lock owned by the current thread.


## -parameters




### -param Lock [in, out]

Opaque push lock pointer of type **PEX_PUSH_LOCK**. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>. 


## -remarks



<b>FltReleasePushLock</b> releases a push lock that was previously acquired by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541667">FltAcquirePushLockExclusive</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541672">FltAcquirePushLockShared</a>. 

Because <b>FltReleasePushLock</b> reenables normal kernel APC delivery, it is not necessary to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a> after calling <b>FltReleasePushLock</b>. 

For more information about push locks, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>. 

To acquire a push lock for exclusive access, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541667">FltAcquirePushLockExclusive</a>. 

To acquire a push lock for shared access, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541672">FltAcquirePushLockShared</a>. 

To initialize a push lock, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>. 

To delete a push lock, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541993">FltDeletePushLock</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541667">FltAcquirePushLockExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541672">FltAcquirePushLockShared</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541993">FltDeletePushLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a>
 

 

