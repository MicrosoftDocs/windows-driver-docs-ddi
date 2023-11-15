---
UID: NF:fltkernel.FltWriteFileEx
title: FltWriteFileEx function (fltkernel.h)
description: Learn more about the FltWriteFileEx function.
tech.root: ifsk
ms.date: 11/14/2023
keywords: ["FltWriteFileEx function"]
ms.keywords: FltWriteFileEx, FltWriteFileEx function [Installable File System Drivers], fltkernel/FltWriteFileEx, ifsk.fltwritefileex
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltWriteFileEx
 - fltkernel/FltWriteFileEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltWriteFileEx
---

# FltWriteFileEx function

## -description

**FltWriteFileEx** is used to write data to an open file, stream, or device. This function extends [**FltWriteFile**](nf-fltkernel-fltwritefile.md) to allow the optional use of an MDL for write data instead of a mapped buffer address.

## -parameters

### -param InitiatingInstance [in]

An opaque instance pointer for the minifilter driver instance that the operation is to be sent to. The instance must be attached to the volume where the file resides. This parameter is required and cannot be NULL.

### -param FileObject [in]

A pointer to a [**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md) for the file that the data is to be written to. This file object must be currently open. Calling **FltWriteFileEx** when the file object is not yet open or is no longer open (for example, in a pre-create or post-cleanup callback routine) causes the system to ASSERT on a checked build. This parameter is required and cannot be NULL.

### -param ByteOffset [in, optional]

A pointer to a caller-allocated variable that specifies the starting byte offset within the file where the write operation is to begin.

If this offset is supplied, or if the FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET** flag is specified in the **Flags** parameter, **FltWriteFileEx** does not update the file object's **CurrentByteOffset** field.

If the file object that **FileObject** points to was opened for synchronous I/O, the caller of **FltWriteFileEx** can specify that the current file position offset be used instead of an explicit **ByteOffset** value by setting this parameter to NULL. If the current file position is used, the file object's **CurrentByteOffset** field is updated by adding the number of bytes written when it completes the write operation.

If the file object that **FileObject** points to was opened for asynchronous I/O, this parameter is required and cannot be NULL.

**FltWriteFileEx** doesn't support the FILE_WRITE_TO_END_OF_FILE flag.

### -param Length [in]

The size, in bytes, of the buffer that the **Buffer** parameter points to. If an MDL is provided in **Mdl**, then **Length** is the size of the data that MDL describes.

### -param Buffer [in]

A pointer to a buffer that contains the data to be written to the file. If the file is opened for noncached I/O, this buffer be must be aligned in accordance with the alignment requirement of the underlying storage device. Minifilter drivers can allocate such an aligned buffer by calling [**FltAllocatePoolAlignedWithTag**](nf-fltkernel-fltallocatepoolalignedwithtag.md).

If an MDL is provided in **Mdl**, **Buffer** must be NULL.

### -param Flags [in]

A bitmask of flags that specify the type of write operation to be performed.

| Flag | Meaning |
| ---- | ------- |
| FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET | Minifilter drivers can set this flag to specify that **FltWriteFileEx**  will not update the file object's **CurrentByteOffset** field. |
| FLTFL_IO_OPERATION_NON_CACHED | Minifilter drivers can set this flag to specify a noncached write, even if the file object was not opened with FILE_NO_INTERMEDIATE_BUFFERING. |
| FLTFL_IO_OPERATION_PAGING | Minifilter drivers can set this flag to specify a paging write. |
| FLTFL_IO_OPERATION_SYNCHRONOUS_PAGING | Minifilter drivers can set this flag to specify a synchronous paging I/O write. Minifilter drivers that set this flag must also set the FLTFL_IO_OPERATION_PAGING flag. This flag is available starting with Windows Vista. |

### -param BytesWritten [out, optional]

A pointer to a caller-allocated variable that receives the number of bytes written to the file. If **CallbackRoutine** is not NULL, this parameter is ignored. Otherwise, this parameter is optional and can be NULL.

### -param CallbackRoutine [in, optional]

A pointer to a [**PFLT_COMPLETED_ASYNC_IO_CALLBACK**](nc-fltkernel-pflt_completed_async_io_callback.md)-typed callback routine to call when the write operation is complete. This parameter is optional and can be NULL.

### -param CallbackContext [in, optional]

A context pointer to be passed to the routine in **CallbackRoutine** if one is present. This parameter is optional and can be NULL. If **CallbackRoutine** is NULL, this parameter is ignored.

### -param Key [in, optional]

An optional key associated with a file object lock.

### -param Mdl [in, optional]

An optional MDL that describes the data to write. If a buffer is provided in **Buffer**, then **Mdl** must be NULL.

## -returns

**FltWriteFileEx** returns the NTSTATUS value that was returned by the file system.

## -remarks

A minifilter driver calls **FltWriteFileEx** to write data to an open file.

**FltWriteFileEx** causes a write request to be sent to the minifilter driver instances attached below the initiating instance and to the file system. The specified instance and the instances attached above it do not receive the write request.

**FltWriteFileEx** performs noncached I/O if either of the following is true:

* The caller set the FLTFL_IO_OPERATION_NON_CACHED flag in the **Flags** parameter.

* The file object was opened for noncached I/O. Usually, this is done by specifying the **FILE_NO_INTERMEDIATE_BUFFERING****CreateOptions** flag in the preceding call to [**FltCreateFile**](nf-fltkernel-fltcreatefile.md), [**FltCreateFileEx**](nf-fltkernel-fltcreatefileex.md), or [**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md).

Noncached I/O imposes the following restrictions on the parameter values passed to **FltWriteFileEx**:

* The buffer that the **Buffer** parameter points to must be aligned in accordance with the alignment requirement of the underlying storage device. To allocate such an aligned buffer, call [**FltAllocatePoolAlignedWithTag**](nf-fltkernel-fltallocatepoolalignedwithtag.md).

* The byte offset that the **ByteOffset** parameter points to must be a nonnegative multiple of the volume's sector size.

* The length specified in the **Length** parameter must be a nonnegative multiple of the volume's sector size.

If the value of the **CallbackRoutine** parameter is not NULL, the write operation is performed asynchronously.

If the value of the **CallbackRoutine** parameter is NULL, the write operation is performed synchronously. That is, **FltWriteFileEx** waits until the write operation is complete before returning. This is true even if the file object that **FileObject** points to was opened for asynchronous I/O.

If multiple threads call **FltWriteFileEx** for the same file object, and the file object was opened for synchronous I/O, the filter manager does not attempt to serialize I/O on the file. In this respect, **FltWriteFileEx** differs from [**ZwWriteFile**](../wdm/nf-wdm-zwwritefile.md).

The **Mdl** parameter is provided as a convenience when a minifilter already has an MDL available. The MDL is used directly and the additional step of mapping an address for **Buffer** can be avoided.

## -see-also

[**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md)

[**FltAllocatePoolAlignedWithTag**](nf-fltkernel-fltallocatepoolalignedwithtag.md)

[**FltCreateFile**](nf-fltkernel-fltcreatefile.md)

[**FltCreateFileEx**](nf-fltkernel-fltcreatefileex.md)

[**FltReadFileEx**](nf-fltkernel-fltreadfileex.md)

[**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md)

[**PFLT_COMPLETED_ASYNC_IO_CALLBACK**](nc-fltkernel-pflt_completed_async_io_callback.md)

[**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md)

[**ZwReadFile**](../wdm/nf-wdm-zwreadfile.md)

[**ZwWriteFile**](../wdm/nf-wdm-zwwritefile.md)
