---
UID: NF:ntifs.IoReleaseVpbSpinLock
title: IoReleaseVpbSpinLock function (ntifs.h)
description: The IoReleaseVpbSpinLock routine releases the Volume Parameter Block (VPB) spin lock.
old-location: ifsk\ioreleasevpbspinlock.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["IoReleaseVpbSpinLock function"]
ms.keywords: IoReleaseVpbSpinLock, IoReleaseVpbSpinLock routine [Installable File System Drivers], ifsk.ioreleasevpbspinlock, ioref_6ccdef5f-9874-4e93-8d91-a05b80d5cecf.xml, ntifs/IoReleaseVpbSpinLock
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoReleaseVpbSpinLock
 - ntifs/IoReleaseVpbSpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoReleaseVpbSpinLock
---

# IoReleaseVpbSpinLock function


## -description

The <b>IoReleaseVpbSpinLock</b> routine releases the Volume Parameter Block (VPB) spin lock.

## -parameters

### -param Irql [in]


Saved IRQL value returned by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioacquirevpbspinlock">IoAcquireVpbSpinLock</a> when the VPB spin lock was acquired.

## -remarks

This routine is the reciprocal to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioacquirevpbspinlock">IoAcquireVpbSpinLock</a>. Every successful call to <b>IoAcquireVpbSpinLock</b> must be matched by a subsequent call to <b>IoReleaseVpbSpinLock</b>. 

Before using <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioacquirevpbspinlock">IoAcquireVpbSpinLock</a> and <b>IoReleaseVpbSpinLock</b>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample. 

The holder of the VPB spin lock executes at IRQL DISPATCH_LEVEL after calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioacquirevpbspinlock">IoAcquireVpbSpinLock</a>. <b>IoReleaseVpbSpinLock</b> restores the caller's original IRQL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioacquirevpbspinlock">IoAcquireVpbSpinLock</a>
