---
UID: NF:fltkernel.FltFlushBuffers2
title: FltFlushBuffers2 function
author: windows-driver-content
description: A minifilter driver calls FltFlushBuffers2 to send a flush request to the file system for a given file.
tech.root: ifsk
ms.assetid: 183306c4-79fc-4356-81b3-658b307c7200
ms.author: windowsdriverdev
ms.date: 1/11/19
ms.topic: function
f1_keywords:
 - "fltkernel/FltFlushBuffers2"
ms.keywords: FltFlushBuffers2, FltFlushBuffers, IRP_MJ_FLUSH_BUFFERS
req.header: fltkernel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- fltkernel.h
api_name: 
- FltFlushBuffers2
product:
 - Windows
targetos: Windows
dev_langs:
- c++
ms.custom: 19H1
---

# FltFlushBuffers2 function

## -description

A minifilter driver calls **FltFlushBuffers2** to send a flush request to the file system for a given file.

## -parameters

### -param Instance

Opaque instance pointer for the calling minifilter driver instance. This parameter is required and cannot be **NULL**.

### -param FileObject

File object pointer for the file or volume to be flushed. This parameter is required and cannot be **NULL**.

### -param FlushType

Specifies the type of flush that the file system should do on the file. *FlushType* can be one of the following:

| FlushType Operation Value | Description |
| ------------------------- | ----------- |
| **0** | If *FileObject* is for a file, both the file data and metadata in the file cache will be written, and the underlying storage will be synchronized to flush its cache. If *FileObject* is for a volume, the file system will cause both the file data and metadata for all modified files on the volume will be written, and the underlying storage to be synchronized to flush its cache. This operation is equivalent to [**FltFlushBuffers**](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltflushbuffers). |
| **FLUSH_FLAGS_FILE_DATA_ONLY** | If the file is on an NTFS file system, only file data in the file cache will be written. No metadata is written and the underlying storage is not synchronized to flush its cache. This flag is not valid if *FileObject* is for a volume. |
| **FLUSH_FLAGS_NO_SYNC** | If the file is on an NTFS file system, file data and metadata in the file cache will be written. The underlying storage will not be synchronized to flush its cache. This flag is not valid if *FileObject* is for a volume. |
| **FLUSH_FLAGS_FILE_DATA_SYNC_ONLY** | If the file is on an NTFS file system, file data in the file cache will be written. No metadata is written. The underlying storage is synchronized to flush its cache. This flag is not valid if *FileObject* is for a volume or directory. |

## -returns

**FltFlushBuffers2** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_MEDIA_WRITE_PROTECTED** | The file resides on a write-protected volume. This is an error code. |
| **STATUS_VOLUME_DISMOUNTED** | The file resides on a volume that is not currently mounted. This is an error code. |

## -remarks

A minifilter driver can call **FltFlushBuffers2** to issue an [IRP_MJ_FLUSH_BUFFERS](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers) request to the file system for a given file. The flush operation is synchronous and is issued to the instance(s) below the specified *Instance*.

If the file is on an NTFS file system, the minifilter can control the type of flush through the *FlushType* parameter.

## -see-also

[**FltFlushBuffers**](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltflushbuffers)

[IRP_MJ_FLUSH_BUFFERS](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers)
