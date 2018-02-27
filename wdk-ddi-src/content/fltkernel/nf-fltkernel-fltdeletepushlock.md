---
UID: NF:fltkernel.FltDeletePushLock
title: FltDeletePushLock function
author: windows-driver-content
description: The FltDeletePushLock routine deletes a given push lock.
old-location: ifsk\fltdeletepushlock.htm
old-project: ifsk
ms.assetid: 93b4914c-53a1-4594-ac8d-4be1b0c9e4d7
ms.author: windowsdriverdev
ms.date: 2/16/2018
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


## -syntax


````
VOID FltDeletePushLock(
  _In_ PEX_PUSH_LOCK PushLock
);
````


## -parameters




### -param PushLock [in]

Opaque push lock pointer. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 


## -returns



None




## -remarks



This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

After calling <b>FltDeletePushLock</b>, the caller can free the memory that it allocated for the push lock. 

For more information about push locks, see the reference entry for <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 

To acquire a push lock for exclusive access, call <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md">FltAcquirePushLockExclusive</a>. 

To acquire a push lock for shared access, call <a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>. 

To release a push lock, call <a href="..\fltkernel\nf-fltkernel-fltreleasepushlock.md">FltReleasePushLock</a>. 

To initialize a push lock, call <a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md">FltAcquirePushLockExclusive</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializepushlock.md">FltInitializePushLock</a>



<a href="..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md">FltAcquirePushLockShared</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasepushlock.md">FltReleasePushLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeletePushLock routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

