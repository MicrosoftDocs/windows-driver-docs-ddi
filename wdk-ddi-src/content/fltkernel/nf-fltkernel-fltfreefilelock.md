---
UID: NF:fltkernel.FltFreeFileLock
title: FltFreeFileLock function (fltkernel.h)
description: The FltFreeFileLock routine uninitializes and frees an initialized FILE_LOCK structure.
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FltFreeFileLock function"]
ms.keywords: FltApiRef_e_to_o_823e2511-8afe-4151-bbac-a9481c079068.xml, FltFreeFileLock, FltFreeFileLock routine [Installable File System Drivers], fltkernel/FltFreeFileLock, ifsk.fltfreefilelock
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
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFreeFileLock
 - fltkernel/FltFreeFileLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltFreeFileLock
---

# FltFreeFileLock function

## -description

The **FltFreeFileLock** routine uninitializes and frees an initialized FILE_LOCK structure.

## -parameters

### -param FileLock [in]

Pointer to the FILE_LOCK structure. This structure must have been initialized by a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md) or [**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md).

## -returns

None

## -remarks

The FILE_LOCK structure is opaque: that is, its members are reserved for system use.

To allocate and initialize a new file lock structure, call [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

It is a programming error to call **FltFreeFileLock** for a FILE_LOCK structure that has already been uninitialized by a call to [**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md).

## -see-also

[**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md)

[**FltCheckLockForReadAccess**](nf-fltkernel-fltchecklockforreadaccess.md)

[**FltCheckLockForWriteAccess**](nf-fltkernel-fltchecklockforwriteaccess.md)

[**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md)

[**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md)

[**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md)

[**FsRtlFreeFileLock**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfreefilelock.md)
