---
UID: NF:ntifs.FsRtlMdlWriteCompleteDev
title: FsRtlMdlWriteCompleteDev function (ntifs.h)
description: The FltFastIoMdlWriteComplete routine frees the resources that FltFastIoPrepareMdlWrite allocated.
old-location: ifsk\fltfastiomdlwritecomplete.htm
tech.root: ifsk
ms.assetid: 7B67BB47-6F95-4B1A-A823-F796529D5C48
ms.date: 04/16/2018
keywords: ["FsRtlMdlWriteCompleteDev function"]
ms.keywords: FsRtlMdlWriteCompleteDev, FsRtlMdlWriteCompleteDev routine [Installable File System Drivers], fltkernel/FsRtlMdlWriteCompleteDev
req.header: ntifs.h
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
ms.custom: RS5
f1_keywords:
 - FsRtlMdlWriteCompleteDev
 - ntifs/FsRtlMdlWriteCompleteDev
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlMdlWriteCompleteDev
dev_langs:
 - c++
---

# FsRtlMdlWriteCompleteDev function


## -description

The **FsRtlMdlWriteCompleteDev** routine frees the resources that [FsRtlPrepareMdlWriteDev](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev.md) allocated.

## -parameters

### -param FileObject 

[in]
A pointer to the file object.

### -param FileOffset 

[in]
A pointer to a value that specifies the starting byte offset within the cache that holds the data.

### -param MdlChain 

[in]
A pointer to a linked list of memory descriptor lists (MDLs) that [FsRtlPrepareMdlWriteDev](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev.md) allocated.

### -param DeviceObject

[ in, optional ] A pointer to a device object on which the file is opened.

## -returns

The **FsRtlMdlWriteCompleteDev** routine returns **TRUE** if the operation succeeds and **FALSE** if the operation fails or if the FO_WRITE_THROUGH flag is set in the file object.

## -remarks

The **FsRtlMdlWriteCompleteDev** routine frees the memory descriptor lists (MDLs) that [FsRtlPrepareMdlWriteDev](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev.md) allocated and unlocks the cache memory that **FsRtlPrepareMdlWriteDev** locked.

If the FO_WRITE_THROUGH flag is set on the file object pointed to by the <i>FileObject</i> parameter, **FsRtlMdlWriteCompleteDev** immediately flushes the cached memory to disk. This flush operation re-enters the file system and can cause **FsRtlMdlWriteCompleteDev** to raise an exception if the flush operation fails. 

Each call to [FsRtlPrepareMdlWriteDev](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev.md) must be followed by a call to **FsRtlMdlWriteCompleteDev**.

## -see-also

[FsRtlPrepareMdlWriteDev](./nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev.md)
