---
UID: NF:fltkernel.FltCheckLockForWriteAccess
title: FltCheckLockForWriteAccess function (fltkernel.h)
description: The FltCheckLockForWriteAccess routine determines whether the caller has write access to a locked byte range of a file.
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FltCheckLockForWriteAccess function"]
ms.keywords: FltApiRef_a_to_d_c9957537-90d0-4830-bba1-1043f450c367.xml, FltCheckLockForWriteAccess, FltCheckLockForWriteAccess routine [Installable File System Drivers], fltkernel/FltCheckLockForWriteAccess, ifsk.fltchecklockforwriteaccess
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP SP2
req.target-min-winversvr: Windows Server 2003 SP1
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
 - FltCheckLockForWriteAccess
 - fltkernel/FltCheckLockForWriteAccess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltCheckLockForWriteAccess
---

# FltCheckLockForWriteAccess function

## -description

The **FltCheckLockForWriteAccess** routine determines whether the caller has write access to a locked byte range of a file.

## -parameters

### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md) or [**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md).

### -param CallbackData [in]

Pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure for the [**IRP_MJ_WRITE**](/windows-hardware/drivers/ifs/irp-mj-write) operation.

## -returns

**FltCheckLockForWriteAccess** returns TRUE if the process has write access, FALSE otherwise.

## -remarks

**FltCheckLockForWriteAccess** checks whether the caller has write access to the entire byte range indicated in the callback data structure.

**FltCheckLockForWriteAccess** does not complete the [**IRP_MJ_READ**](/windows-hardware/drivers/ifs/irp-mj-write) operation.

To allocate and initialize a new file lock structure, call [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

To free an initialized FILE_LOCK structure, call [**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md).

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md)

[**FltCheckLockForReadAccess**](nf-fltkernel-fltchecklockforreadaccess.md)

[**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md)

[**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md)

[**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md)

[**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md)

[**FsRtlCheckLockForWriteAccess**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess.md)

[**IRP_MJ_WRITE**](/windows-hardware/drivers/ifs/irp-mj-write)
