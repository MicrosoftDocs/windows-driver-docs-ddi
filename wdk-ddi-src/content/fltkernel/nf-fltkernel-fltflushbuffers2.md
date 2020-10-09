---
UID: NF:fltkernel.FltFlushBuffers2
title: FltFlushBuffers2 function
description: A minifilter driver calls FltFlushBuffers2 to send a flush request to the file system for a given file.
tech.root: ifsk
ms.assetid: 183306c4-79fc-4356-81b3-658b307c7200
ms.date: 01/02/2020
keywords: ["FltFlushBuffers2 function"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - FltFlushBuffers2
 - fltkernel/FltFlushBuffers2
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
dev_langs:
 - c++
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
| 0 | If *FileObject* is for a file, both the file data and metadata in the file cache will be written, and the underlying storage will be synchronized to flush its cache. If *FileObject* is for a volume, the file system will cause both the file data and metadata for all modified files on the volume will be written, and the underlying storage to be synchronized to flush its cache. This operation is equivalent to [**FltFlushBuffers**](./nf-fltkernel-fltflushbuffers.md). |
| FLT_FLUSH_TYPE_FLUSH_AND_PURGE | Same as 0 (**FltFlushBuffers**), except that the cache is also purged after the flush completes. |
| FLT_FLUSH_TYPE_FILE_DATA_ONLY | If the file is on an NTFS file system, only file data in the file cache will be written. No metadata is written and the underlying storage is not synchronized to flush its cache. This flag is not valid if *FileObject* is for a volume. |
| FLT_FLUSH_TYPE_NO_SYNC | If the file is on an NTFS file system, file data and metadata in the file cache will be written. The underlying storage will not be synchronized to flush its cache. This flag is not valid if *FileObject* is for a volume. |
| FLT_FLUSH_TYPE_DATA_SYNC_ONLY | If the file is on an NTFS file system, file data in the file cache will be written. No metadata is written. The underlying storage is synchronized to flush its cache. This flag is not valid if *FileObject* is for a volume or directory. |

### -param CallbackData

Pointer to optional callback data used to propagate the caller's IRP extension. See [**FltPropagateIrpExtension**](./nf-fltkernel-fltpropagateirpextension.md).

## -returns

**FltFlushBuffers2** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_MEDIA_WRITE_PROTECTED** | The file resides on a write-protected volume. This is an error code. |
| **STATUS_VOLUME_DISMOUNTED** | The file resides on a volume that is not currently mounted. This is an error code. |

## -remarks

A minifilter driver can call **FltFlushBuffers2** to issue an [IRP_MJ_FLUSH_BUFFERS](/windows-hardware/drivers/ifs/irp-mj-flush-buffers) request to the file system for a given file. The flush operation is synchronous and is issued to the instance(s) below the specified *Instance*.

If the file is on an NTFS file system, the minifilter can control the type of flush through the *FlushType* parameter.

## -see-also

[**FltFlushBuffers**](./nf-fltkernel-fltflushbuffers.md)

[**FltPropagateIrpExtension**](./nf-fltkernel-fltpropagateirpextension.md)

[IRP_MJ_FLUSH_BUFFERS](/windows-hardware/drivers/ifs/irp-mj-flush-buffers)