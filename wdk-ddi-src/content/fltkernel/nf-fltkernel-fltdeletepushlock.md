---
UID: NF:fltkernel.FltDeletePushLock
title: FltDeletePushLock function
author: windows-driver-content
description: The FltDeletePushLock routine deletes a given push lock.
old-location: ifsk\fltdeletepushlock.htm
old-project: ifsk
ms.assetid: 93b4914c-53a1-4594-ac8d-4be1b0c9e4d7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_a_to_d_876710d9-ee11-413f-8889-f9a34cb423fd.xml, FltDeletePushLock, FltDeletePushLock routine [Installable File System Drivers], fltkernel/FltDeletePushLock, ifsk.fltdeletepushlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	FltDeletePushLock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltDeletePushLock function


## -description


The <b>FltDeletePushLock</b> routine deletes a given push lock. 


## -parameters




### -param PushLock [in]

Opaque push lock pointer. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>. 


## -returns



None




## -remarks



This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

After calling <b>FltDeletePushLock</b>, the caller can free the memory that it allocated for the push lock. 

For more information about push locks, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>. 

To acquire a push lock for exclusive access, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541667">FltAcquirePushLockExclusive</a>. 

To acquire a push lock for shared access, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541672">FltAcquirePushLockShared</a>. 

To release a push lock, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544326">FltReleasePushLock</a>. 

To initialize a push lock, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541667">FltAcquirePushLockExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541672">FltAcquirePushLockShared</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543297">FltInitializePushLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544326">FltReleasePushLock</a>
 

 

