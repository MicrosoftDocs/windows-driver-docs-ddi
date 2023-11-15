---
UID: NF:fltkernel.FltWriteFile
title: FltWriteFile function (fltkernel.h)
description: Learn more about the FltWriteFile function.
tech.root: ifsk
ms.date: 11/15/2023
keywords: ["FltWriteFile function"]
ms.keywords: FltApiRef_p_to_z_8d4d2b16-fa86-4084-8dad-879d4908f2fe.xml, FltWriteFile, FltWriteFile function [Installable File System Drivers], fltkernel/FltWriteFile, ifsk.fltwritefile
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
 - FltWriteFile
 - fltkernel/FltWriteFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltWriteFile
---

# FltWriteFile function

## -description

**FltWriteFile** is used to write data to an open file, stream, or device.

## -parameters

### -param InitiatingInstance [in]

An opaque instance pointer for the minifilter driver instance that the operation is to be sent to. The instance must be attached to the volume where the file resides. This parameter is required and cannot be NULL.

### -param FileObject [in]

Pointer to a [**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md) for the file that the data is to be written to. This file object must be currently open. Calling **FltWriteFile** when the file object is not yet open or is no longer open (for example, in a pre-create or post-cleanup callback routine) causes the system to ASSERT on a checked build. This parameter is required and cannot be NULL.

### -param ByteOffset [in, optional]

Pointer to a caller-allocated variable that specifies the starting byte offset within the file where the read operation is to begin.

If **ByteOffset** is specified, the I/O is performed at that offset, regardless of the current value of the file object’s **CurrentByteOffset** field.

* If the file was opened for synchronous I/O (FO_SYNCHRONOUS_IO is set in the file object’s **Flags** field), the caller can set **ByteOffset->LowPart** to FILE_USE_FILE_POINTER_POSITION and **ByteOffset->HighPart** to -1 to have the I/O performed at the file object’s **CurrentByteOffset** field. If the file wasn't opened for synchronous I/O, using FILE_USE_FILE_POINTER_POSITION is an error.
* The caller can set **ByteOffset->LowPart** to FILE_WRITE_TO_END_OF_FILE and **ByteOffset->HighPart** to -1 to start the write at the end of the file (i.e., perform an appending write).

If **ByteOffset** isn't specified:

* If the file wasn't opened for synchronous I/O, that's an error.
* Otherwise, the I/O is performed at the file object’s **CurrentByteOffset**.

If the file object was opened for synchronous I/O, the **CurrentByteOffset** field gets updated unless the caller passes the FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET flag.

* Note: the file system still updates **CurrentByteOffset** in this case. Filter Manager saves the **CurrentByteOffset** value before sending the I/O down the stack and restores it when the I/O returns. From the perspective of the caller of **FltWriteFile** (and filters at higher altitudes) the **CurrrentByteOffset** isn't updated. But filters below the caller see the updated **CurrentByteOffset** value in their post-read/write callbacks.

If the file object wasn't opened for synchronous I/O, the **CurrentByteOffset** field isn't updated regardless of the state of the **ByteOffset** parameter.

If the file object that **FileObject** points to was opened for asynchronous I/O, this parameter is required and can't be NULL.

Prior to Windows 8, the special constants FILE_WRITE_TO_END_OF_FILE and  FILE_USE_FILE_POINTER_POSITION aren't supported for this parameter.

### -param Length [in]

Size, in bytes, of the buffer that the **Buffer** parameter points to.

### -param Buffer [in]

Pointer to a buffer that contains the data to be written to the file. If the file is opened for noncached I/O, this buffer be must be aligned in accordance with the alignment requirement of the underlying storage device. Minifilter drivers can allocate such an aligned buffer by calling [**FltAllocatePoolAlignedWithTag**](nf-fltkernel-fltallocatepoolalignedwithtag.md).

### -param Flags [in]

Bitmask of flags specifying the type of write operation to be performed.

| Flag | Meaning |
| ---- | ------- |
| FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET | Minifilter drivers can set this flag to specify that **FltWriteFile**  will not update the file object's **CurrentByteOffset** field. |
| FLTFL_IO_OPERATION_NON_CACHED | Minifilter drivers can set this flag to specify a noncached write, even if the file object was not opened with FILE_NO_INTERMEDIATE_BUFFERING. |
| FLTFL_IO_OPERATION_PAGING | Minifilter drivers can set this flag to specify a paging write. |
| FLTFL_IO_OPERATION_SYNCHRONOUS_PAGING | Minifilter drivers can set this flag to specify a synchronous paging I/O write. Minifilter drivers that set this flag must also set the FLTFL_IO_OPERATION_PAGING flag. This flag is available starting with Windows Vista. |

### -param BytesWritten [out, optional]

Pointer to a caller-allocated variable that receives the number of bytes written to the file. If **CallbackRoutine** is not NULL, this parameter is ignored. Otherwise, this parameter is optional and can be NULL.

### -param CallbackRoutine [in, optional]

Pointer to a [**PFLT_COMPLETED_ASYNC_IO_CALLBACK**](nc-fltkernel-pflt_completed_async_io_callback.md)-typed callback routine to call when the write operation is complete. This parameter is optional and can be NULL.

### -param CallbackContext [in, optional]

Context pointer to be passed to the **CallbackRoutine** if one is present. This parameter is optional and can be NULL. If **CallbackRoutine** is NULL, this parameter is ignored.

## -returns

**FltWriteFile** returns the NTSTATUS value that was returned by the file system.

## -remarks

A minifilter driver calls **FltWriteFile** to write data to an open file.

**FltWriteFile** causes a write request to be sent to the minifilter driver instances attached below the initiating instance and to the file system. The specified instance and the instances attached above it do not receive the write request.

**FltWriteFile** performs noncached I/O if either of the following is true:

* The caller set the FLTFL_IO_OPERATION_NON_CACHED flag in the **Flags** parameter.

* The file object was opened for noncached I/O. Usually, this is done by specifying the FILE_NO_INTERMEDIATE_BUFFERING **CreateOptions** flag in the preceding call to [**FltCreateFile**](nf-fltkernel-fltcreatefile.md), [**FltCreateFileEx**](nf-fltkernel-fltcreatefileex.md), or [**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md).

Noncached I/O imposes the following restrictions on the parameter values passed to **FltWriteFile**:

* The buffer that the **Buffer** parameter points to must be aligned in accordance with the alignment requirement of the underlying storage device. To allocate such an aligned buffer, call [**FltAllocatePoolAlignedWithTag**](nf-fltkernel-fltallocatepoolalignedwithtag.md).

* The byte offset that the **ByteOffset** parameter points to must be a nonnegative multiple of the volume's sector size.

* The length specified in the **Length** parameter must be a nonnegative multiple of the volume's sector size.

If the value of the **CallbackRoutine** parameter is not NULL, the write operation is performed asynchronously.

If the value of the **CallbackRoutine** parameter is NULL, the write operation is performed synchronously. That is, **FltWriteFile** waits until the write operation is complete before returning. This is true even if the file object that **FileObject** points to was opened for asynchronous I/O. 

If multiple threads call **FltWriteFile** for the same file object, and the file object was opened for synchronous I/O, the Filter Manager does not attempt to serialize I/O on the file. In this respect, **FltWriteFile** differs from [**ZwWriteFile**](../wdm/nf-wdm-zwwritefile.md).

## -see-also

[**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md)

[**FltAllocatePoolAlignedWithTag**](nf-fltkernel-fltallocatepoolalignedwithtag.md)

[**FltCreateFile**](nf-fltkernel-fltcreatefile.md)

[**FltCreateFileEx**](nf-fltkernel-fltcreatefileex.md)

[**FltReadFile**](nf-fltkernel-fltreadfile.md)

[**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md)

[**PFLT_COMPLETED_ASYNC_IO_CALLBACK**](nc-fltkernel-pflt_completed_async_io_callback.md)

[**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md)

[**ZwReadFile**](../wdm/nf-wdm-zwreadfile.md)

[**ZwWriteFile**](../wdm/nf-wdm-zwwritefile.md)
