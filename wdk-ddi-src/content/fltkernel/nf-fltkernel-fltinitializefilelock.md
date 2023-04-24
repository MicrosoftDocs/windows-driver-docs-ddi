---
UID: NF:fltkernel.FltInitializeFileLock
title: FltInitializeFileLock function (fltkernel.h)
description: The FltInitializeFileLock routine initializes an opaque FILE_LOCK structure that the caller has allocated from paged pool.
old-location: ifsk\fltinitializefilelock.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltInitializeFileLock function"]
ms.keywords: FltApiRef_e_to_o_8e2110a7-bc7b-4a98-b094-c6a7a12e7900.xml, FltInitializeFileLock, FltInitializeFileLock routine [Installable File System Drivers], fltkernel/FltInitializeFileLock, ifsk.fltinitializefilelock
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP SP2 
req.target-min-winversvr: Windows Server 2003 SP1
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
 - FltInitializeFileLock
 - fltkernel/FltInitializeFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltInitializeFileLock
---

# FltInitializeFileLock function

## -description

The **FltInitializeFileLock** routine initializes an opaque [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure that the caller has allocated from paged pool.

## -parameters

### -param FileLock [out]

Pointer to an uninitialized [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure.

## -returns

None

## -remarks

The [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure is opaque: that is, its members are reserved for system use.

Once initialized, the [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure can be used to lock a byte range in a file by calling [**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md).

It is a programming error to call **FltInitializeFileLock** for a [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure that has already been initialized by **FltInitializeFileLock** or [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md), unless the structure has been uninitialized by a subsequent call to [**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md).

When the [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure is no longer needed, it can be uninitialized by calling [**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md). The uninitialized **FILE_LOCK** structure can then be initialized for reuse by calling **FltInitializeFileLock**.

To allocate and initialize a new opaque [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure, call [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

To free an initialized [**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md) structure, call [**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md).

## -see-also

[**FILE_LOCK**](../ntifs/ns-ntifs-file_lock.md)

[**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md)

[**FltCheckLockForReadAccess**](nf-fltkernel-fltchecklockforreadaccess.md)

[**FltCheckLockForWriteAccess**](nf-fltkernel-fltchecklockforwriteaccess.md)

[**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md)

[**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md)

[**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md)

[**FsRtlInitializeFileLock**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock.md)
