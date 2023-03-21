---
UID: NF:fltkernel.FltUninitializeFileLock
title: FltUninitializeFileLock function (fltkernel.h)
description: The FltUninitializeFileLock routine uninitializes a FILE_LOCK structure.
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FltUninitializeFileLock function"]
ms.keywords: FltApiRef_p_to_z_ad1332a2-5434-423c-91d6-de939e1cb28a.xml, FltUninitializeFileLock, FltUninitializeFileLock routine [Installable File System Drivers], fltkernel/FltUninitializeFileLock, ifsk.fltuninitializefilelock
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
 - FltUninitializeFileLock
 - fltkernel/FltUninitializeFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltUninitializeFileLock
---

# FltUninitializeFileLock function

## -description

The **FltUninitializeFileLock** routine uninitializes a FILE_LOCK structure.

## -parameters

### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md) or [**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md).

## -returns

None

## -remarks

**FltUninitializeFileLock** uninitializes an initialized FILE_LOCK structure, freeing all file locks and completing any outstanding lock operations. The uninitialized FILE_LOCK structure can be initialized for reuse by a subsequent call to [**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md).

**FltUninitializeFileLock** can be used to uninitialize a FILE_LOCK structure allocated by a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md). Do not use **FltUninitializeFileLock** for such a FILE_LOCK structure unless the structure is to be initialized for reuse. It is a programming error to call [**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md) for an uninitialized FILE_LOCK structure.

To allocate and initialize a new file lock structure, call [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

To free an initialized FILE_LOCK structure, call [**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md).

## -see-also

[**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md)

[**FltCheckLockForReadAccess**](nf-fltkernel-fltchecklockforreadaccess.md)

[**FltCheckLockForWriteAccess**](nf-fltkernel-fltchecklockforwriteaccess.md)

[**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md)

[**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md)

[**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md)

[**FsRtlUninitializeFileLock**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md)
