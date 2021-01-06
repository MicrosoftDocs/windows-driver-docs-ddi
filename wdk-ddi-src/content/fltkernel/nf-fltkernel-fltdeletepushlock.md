---
UID: NF:fltkernel.FltDeletePushLock
title: FltDeletePushLock function (fltkernel.h)
description: The FltDeletePushLock routine deletes a given push lock.
old-location: ifsk\fltdeletepushlock.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltDeletePushLock function"]
ms.keywords: FltApiRef_a_to_d_876710d9-ee11-413f-8889-f9a34cb423fd.xml, FltDeletePushLock, FltDeletePushLock routine [Installable File System Drivers], fltkernel/FltDeletePushLock, ifsk.fltdeletepushlock
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
 - FltDeletePushLock
 - fltkernel/FltDeletePushLock
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
---

# FltDeletePushLock function


## -description

The <b>FltDeletePushLock</b> routine deletes a given push lock.

## -parameters

### -param PushLock 

[in]
Opaque push lock pointer. This pointer must have been initialized by a previous call to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>.

## -returns

None

## -remarks

This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

After calling <b>FltDeletePushLock</b>, the caller can free the memory that it allocated for the push lock. 

For more information about push locks, see the reference entry for <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>. 

To acquire a push lock for exclusive access, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockexclusive">FltAcquirePushLockExclusive</a>. 

To acquire a push lock for shared access, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockshared">FltAcquirePushLockShared</a>. 

To release a push lock, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasepushlock">FltReleasePushLock</a>. 

To initialize a push lock, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockexclusive">FltAcquirePushLockExclusive</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockshared">FltAcquirePushLockShared</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializepushlock">FltInitializePushLock</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasepushlock">FltReleasePushLock</a>
