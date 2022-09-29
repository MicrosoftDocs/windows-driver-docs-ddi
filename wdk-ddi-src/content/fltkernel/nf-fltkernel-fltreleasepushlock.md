---
UID: NF:fltkernel.FltReleasePushLock
title: FltReleasePushLock macro (fltkernel.h)
description: The FltReleasePushLock routine releases a specified push lock owned by the current thread.
old-location: ifsk\fltreleasepushlock.htm
tech.root: ifsk
ms.date: 08/11/2022
keywords: ["FltReleasePushLock macro"]
ms.keywords: FltApiRef_p_to_z_31e736a4-7790-443f-a6bf-e43d3823ad27.xml, FltReleasePushLock, FltReleasePushLock routine [Installable File System Drivers], fltkernel/FltReleasePushLock, ifsk.fltreleasepushlock
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltReleasePushLock
 - fltkernel/FltReleasePushLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltReleasePushLock
---

# FltReleasePushLock macro

## -description

The **FltReleasePushLock** routine releases a specified push lock owned by the current thread.

## -parameters

### -param PushLock [in, out]

Opaque push lock pointer of type **PEX_PUSH_LOCK**. This pointer must have been initialized by a previous call to [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

## -returns

None.

## -remarks

**FltReleasePushLock** releases a push lock that was previously acquired by calling [**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md) or [**FltAcquirePushLockShared**](nf-fltkernel-fltacquirepushlockshared.md).

Because **FltAcquirePushLockExclusive** disables normal kernel APC delivery, it is not necessary to call [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem) before calling **FltAcquirePushLockExclusive**.

For more information about push locks, see the reference entry for [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

To acquire a push lock for exclusive access, call [**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md).

To acquire a push lock for shared access, call [**FltAcquirePushLockShared**](nf-fltkernel-fltacquirepushlockshared.md).

To initialize a push lock, call [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

To delete a push lock, call [**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md).

## -see-also

[**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md)

[**FltAcquirePushLockShared**](nf-fltkernel-fltacquirepushlockshared.md)

[**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md)

[**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md)

[**FltReleasePushLockEx**](nf-fltkernel-fltreleasepushlockex.md)

[**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem)

[**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md)
