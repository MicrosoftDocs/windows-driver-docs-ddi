---
UID: NF:fltkernel.FltDeletePushLock
title: FltDeletePushLock function (fltkernel.h)
description: The FltDeletePushLock routine deletes a given push lock.
old-location: ifsk\fltdeletepushlock.htm
tech.root: ifsk
ms.assetid: 93b4914c-53a1-4594-ac8d-4be1b0c9e4d7
ms.date: 04/16/2018
keywords: ["FltDeletePushLock function"]
ms.keywords: FltApiRef_a_to_d_876710d9-ee11-413f-8889-f9a34cb423fd.xml, FltDeletePushLock, FltDeletePushLock routine [Installable File System Drivers], fltkernel/FltDeletePushLock, ifsk.fltdeletepushlock
f1_keywords:
 - "fltkernel/FltDeletePushLock"
 - "FltDeletePushLock"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltDeletePushLock
targetos: Windows
req.typenames: 
---

# FltDeletePushLock function


## -description


The <b>FltDeletePushLock</b> routine deletes a given push lock. 


## -parameters




### -param PushLock 
[in]
Opaque push lock pointer. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>. 


## -returns



None




## -remarks



This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

After calling <b>FltDeletePushLock</b>, the caller can free the memory that it allocated for the push lock. 

For more information about push locks, see the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>. 

To acquire a push lock for exclusive access, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockexclusive">FltAcquirePushLockExclusive</a>. 

To acquire a push lock for shared access, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockshared">FltAcquirePushLockShared</a>. 

To release a push lock, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasepushlock">FltReleasePushLock</a>. 

To initialize a push lock, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockexclusive">FltAcquirePushLockExclusive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockshared">FltAcquirePushLockShared</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasepushlock">FltReleasePushLock</a>
 

 

