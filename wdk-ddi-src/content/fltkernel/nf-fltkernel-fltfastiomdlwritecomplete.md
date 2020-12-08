---
UID: NF:fltkernel.FltFastIoMdlWriteComplete
title: FltFastIoMdlWriteComplete function (fltkernel.h)
description: The FltFastIoMdlWriteComplete routine frees the resources that FltFastIoPrepareMdlWrite allocated.
old-location: ifsk\fltfastiomdlwritecomplete.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltFastIoMdlWriteComplete function"]
ms.keywords: FltFastIoMdlWriteComplete, FsRtlMdlWriteCompleteDev, FsRtlMdlWriteCompleteDev routine [Installable File System Drivers], fltkernel/FsRtlMdlWriteCompleteDev, ifsk.fltfastiomdlwritecomplete
req.header: fltkernel.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFastIoMdlWriteComplete
 - fltkernel/FltFastIoMdlWriteComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlMdlWriteCompleteDev
---

# FltFastIoMdlWriteComplete function


## -description

The <b>FltFastIoMdlWriteComplete</b> routine frees the resources that <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiopreparemdlwrite">FltFastIoPrepareMdlWrite</a> allocated.

## -parameters

### -param InitiatingInstance

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

### -param FileObject 

[in]
A pointer to the file object.

### -param FileOffset 

[in]
A pointer to a value that specifies the starting byte offset within the cache that holds the data.

### -param MdlChain 

[in]
A pointer to a linked list of memory descriptor lists (MDLs) that <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiopreparemdlwrite">FltFastIoPrepareMdlWrite</a> allocated.

## -returns

The <b>FltFastIoMdlWriteComplete</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails or if the FO_WRITE_THROUGH flag is set in the file object.

## -remarks

The <b>FltFastIoMdlWriteComplete</b> routine frees the memory descriptor lists (MDLs) that <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiopreparemdlwrite">FltFastIoPrepareMdlWrite</a> allocated and unlocks the cache memory that <b>FltFastIoPrepareMdlWrite</b> locked.

If the FO_WRITE_THROUGH flag is set on the file object pointed to by the <i>FileObject</i> parameter, <b>FltFastIoMdlWriteComplete</b> immediately flushes the cached memory to disk. This flush operation re-enters the file system and can cause <b>FltFastIoMdlWriteComplete</b> to raise an exception if the flush operation fails. 

Each call to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiopreparemdlwrite">FltFastIoPrepareMdlWrite</a> must be followed by a call to <b>FltFastIoMdlWriteComplete</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfastiopreparemdlwrite">FltFastIoPrepareMdlWrite</a>
