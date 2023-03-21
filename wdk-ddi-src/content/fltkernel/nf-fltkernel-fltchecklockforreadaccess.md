---
UID: NF:fltkernel.FltCheckLockForReadAccess
title: FltCheckLockForReadAccess function (fltkernel.h)
description: The FltCheckLockForReadAccess routine determines whether the caller has read access to a locked byte range of a file.
tech.root: ifsk
ms.date: 03/20/2023
keywords: ["FltCheckLockForReadAccess function"]
ms.keywords: FltApiRef_a_to_d_24bd7e02-fdc4-44a3-8d1a-1bb164d26769.xml, FltCheckLockForReadAccess, FltCheckLockForReadAccess routine [Installable File System Drivers], fltkernel/FltCheckLockForReadAccess, ifsk.fltchecklockforreadaccess
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
 - FltCheckLockForReadAccess
 - fltkernel/FltCheckLockForReadAccess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltCheckLockForReadAccess
---

# FltCheckLockForReadAccess function

## -description

The **FltCheckLockForReadAccess** routine determines whether the caller has read access to a locked byte range of a file.

## -parameters

### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md) or [**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md).

### -param CallbackData [in]

Pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure for the [**IRP_MJ_READ**](/windows-hardware/drivers/ifs/irp-mj-read) operation.

## -returns

**FltCheckLockForReadAccess** returns TRUE if the process has read access, FALSE otherwise.

## -remarks

**FltCheckLockForReadAccess** checks whether the caller has read access to the entire byte range indicated in the callback data structure.

**FltCheckLockForReadAccess** does not complete the [**IRP_MJ_READ**](/windows-hardware/drivers/ifs/irp-mj-read) operation.

To allocate and initialize a new file lock structure, call [**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md).

To free an initialized FILE_LOCK structure, call [**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md).

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FltAllocateFileLock**](nf-fltkernel-fltallocatefilelock.md)

[**FltCheckLockForWriteAccess**](nf-fltkernel-fltchecklockforwriteaccess.md)

[**FltFreeFileLock**](nf-fltkernel-fltfreefilelock.md)

[**FltInitializeFileLock**](nf-fltkernel-fltinitializefilelock.md)

[**FltProcessFileLock**](nf-fltkernel-fltprocessfilelock.md)

[**FltUninitializeFileLock**](nf-fltkernel-fltuninitializefilelock.md)

[**FsRtlCheckLockForReadAccess**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess.md)

[**IRP_MJ_READ**](/windows-hardware/drivers/ifs/irp-mj-read)
