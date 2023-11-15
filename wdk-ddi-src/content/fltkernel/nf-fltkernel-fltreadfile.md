---
UID: NF:fltkernel.FltReadFile
title: FltReadFile function (fltkernel.h)
description: Learn more about the FltReadFile function.
tech.root: ifsk
ms.date: 11/14/2023
keywords: ["FltReadFile function"]
ms.keywords: FltApiRef_p_to_z_83c0167c-78df-4692-980b-7a55f531a9db.xml, FltReadFile, FltReadFile function [Installable File System Drivers], fltkernel/FltReadFile, ifsk.fltreadfile
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
 - FltReadFile
 - fltkernel/FltReadFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltReadFile
---

# FltReadFile function

## -description

**FltReadFile** reads data from an open file, stream, or device.

## -parameters

### -param InitiatingInstance [in]

Opaque instance pointer for the minifilter driver instance that the operation is to be sent to. The instance must be attached to the volume where the file resides. This parameter is required and cannot be NULL.

### -param FileObject [in]

Pointer to a [**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md) for the file that the data is to be read from. This file object must be currently open. Calling **FltReadFile** when the file object is not yet open or is no longer open (for example, in a pre-create or post-cleanup callback routine) causes the system to ASSERT on a checked build. This parameter is required and cannot be NULL.

### -param ByteOffset [in, optional]

Pointer to a caller-allocated variable that specifies the starting byte offset within the file where the read operation is to begin.

If this offset is supplied, or if the FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET flag is specified in the **Flags** parameter, the file object's **CurrentByteOffset** isn't updated.

If the file object that **FileObject** points to was opened for synchronous I/O, the caller of **FltReadFile** can specify that the current file position offset be used instead of an explicit **ByteOffset** value by setting this parameter to NULL. If the current file position is used, the file object's **CurrentByteOffset** field is updated by adding the number of bytes read when it completes the read operation.

If the file object that **FileObject** points to was opened for asynchronous I/O, this parameter is required and cannot be NULL.

### -param Length [in]

Size, in bytes, of the buffer that the **Buffer** parameter points to.

### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the data that is read from the file.

### -param Flags [in]

Bitmask of flags specifying the type of read operation to be performed.

| Flag | Meaning |
| ---- | ------- |
| FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET | Minifilter drivers can set this flag to specify that **FltReadFile** should not update the file object's **CurrentByteOffset** field. |
| FLTFL_IO_OPERATION_NON_CACHED | Minifilter drivers can set this flag to specify a noncached read, even if the file object was not opened with FILE_NO_INTERMEDIATE_BUFFERING. |
| FLTFL_IO_OPERATION_PAGING | Minifilter drivers can set this flag to specify a paging read. |
| FLTFL_IO_OPERATION_SYNCHRONOUS_PAGING | Minifilter drivers can set this flag to specify a synchronous paging I/O read. Minifilter drivers that set this flag must also set the FLTFL_IO_OPERATION_PAGING flag. Available starting in Windows Vista. |

### -param BytesRead [out, optional]

Pointer to a caller-allocated variable that receives the number of bytes read from the file. If **CallbackRoutine** is not NULL, this parameter is ignored. Otherwise, this parameter is optional and can be NULL.

### -param CallbackRoutine [in, optional]

Pointer to a [**PFLT_COMPLETED_ASYNC_IO_CALLBACK**](nc-fltkernel-pflt_completed_async_io_callback.md)-typed callback routine to call when the read operation is complete. This parameter is optional and can be NULL.

### -param CallbackContext [in, optional]

Context pointer to be passed to the **CallbackRoutine** if one is present. This parameter is optional and can be NULL. If **CallbackRoutine** is NULL, this parameter is ignored.

## -returns

**FltReadFile** returns the NTSTATUS value that was returned by the file system.

## -remarks

A minifilter driver calls **FltReadFile** to read data from an open file.

**FltReadFile** creates a read request and sends it to the minifilter driver instances attached below the initiating instance, and to the file system. The specified instance and the instances attached above it do not receive the read request.

**FltReadFile** performs noncached I/O if either of the following is true:

* The caller set the FLTFL_IO_OPERATION_NON_CACHED flag in the **Flags** parameter.

* The file object was opened for noncached I/O. Usually, this is done by specifying the FILE_NO_INTERMEDIATE_BUFFERING **CreateOptions** flag in the preceding call to [**FltCreateFile**](nf-fltkernel-fltcreatefile.md), [**FltCreateFileEx**](nf-fltkernel-fltcreatefileex.md), or [**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md).

Noncached I/O imposes the following restrictions on the parameter values passed to **FltReadFile**:

* The buffer that the **Buffer** parameter points to must be aligned in accordance with the alignment requirement of the underlying storage device. To allocate such an aligned buffer, call [**FltAllocatePoolAlignedWithTag**](nf-fltkernel-fltallocatepoolalignedwithtag.md).

* The byte offset that the **ByteOffset** parameter points to must be a nonnegative multiple of the volume's sector size.

* The length specified in the **Length** parameter must be a nonnegative multiple of the volume's sector size.

If an attempt is made to read beyond the end of the file, **FltReadFile** returns an error.

If the value of the **CallbackRoutine** parameter is not NULL, the read operation is performed asynchronously.

If the value of the **CallbackRoutine** parameter is NULL, the read operation is performed synchronously. That is, **FltReadFile** waits until the read operation is complete before returning. This is true even if the file object that **FileObject** points to was opened for asynchronous I/O.

If multiple threads call **FltReadFile** for the same file object, and the file object was opened for synchronous I/O, the Filter Manager does not attempt to serialize I/O on the file. In this respect, **FltReadFile** differs from [**ZwReadFile**](../wdm/nf-wdm-zwreadfile.md).

## -see-also

[**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md)

[**FltAllocatePoolAlignedWithTag**](nf-fltkernel-fltallocatepoolalignedwithtag.md)

[**FltCreateFile**](nf-fltkernel-fltcreatefile.md)

[**FltCreateFileEx**](nf-fltkernel-fltcreatefileex.md)

[**FltWriteFile**](nf-fltkernel-fltwritefile.md)

[**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md)

[**PFLT_COMPLETED_ASYNC_IO_CALLBACK**](nc-fltkernel-pflt_completed_async_io_callback.md)

[**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md)

[**ZwReadFile**](../wdm/nf-wdm-zwreadfile.md)

[**ZwWriteFile**](../wdm/nf-wdm-zwwritefile.md)
