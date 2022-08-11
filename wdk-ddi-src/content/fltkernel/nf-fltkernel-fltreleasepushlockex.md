---
UID: NF:fltkernel.FltReleasePushLockEx
title: FltReleasePushLockEx function (fltkernel.h)
description: The FltReleasePushLockEx routine releases a specified push lock owned by the current thread.
ms.date: 08/11/2022
tech.root: ifsk
keywords: ["FltReleasePushLockEx function"]
ms.keywords: FltReleasePushLockEx
req.header: fltkernel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: FltMgr.lib
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - FltReleasePushLockEx
 - fltkernel/FltReleasePushLockEx
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - FltMgr.sys
api_name:
 - FltReleasePushLockEx
dev_langs:
 - c++
---

# FltReleasePushLockEx function

## -description

The **FltReleasePushLockEx** routine releases a specified push lock owned by the current thread.

## -parameters

### -param PushLock

Opaque push lock pointer of type **PEX_PUSH_LOCK**. This pointer must have been initialized by a previous call to [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

### -param Flags

A bitmask of flags that control the attributes of the lock.

## -returns

None.

## -remarks

**FltReleasePushLockEx** releases a push lock that was previously acquired by calling [**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md) or [**FltAcquirePushLockShared**](nf-fltkernel-fltacquirepushlockshared.md).

Because **FltReleasePushLockEx** reenables normal kernel APC delivery, it is not necessary to call [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem) after calling **FltReleasePushLockEx**.

## -see-also

[**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md)

[**FltAcquirePushLockShared**](nf-fltkernel-fltacquirepushlockshared.md)

[**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md)

[**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md)

[**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem)

[**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md)
