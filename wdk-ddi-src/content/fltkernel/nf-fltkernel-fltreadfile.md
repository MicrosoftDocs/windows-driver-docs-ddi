---
UID: NF:fltkernel.FltReadFile
title: FltReadFile function (fltkernel.h)
description: FltReadFile reads data from an open file, stream, or device.
old-location: ifsk\fltreadfile.htm
tech.root: ifsk
ms.assetid: 3ceacb96-1c60-4310-b96f-6fb396c1d6ce
ms.date: 04/16/2018
keywords: ["FltReadFile function"]
ms.keywords: FltApiRef_p_to_z_83c0167c-78df-4692-980b-7a55f531a9db.xml, FltReadFile, FltReadFile function [Installable File System Drivers], fltkernel/FltReadFile, ifsk.fltreadfile
f1_keywords:
 - "fltkernel/FltReadFile"
 - "FltReadFile"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltReadFile
targetos: Windows
req.typenames: 
---

# FltReadFile function


## -description


<b>FltReadFile</b> reads data from an open file, stream, or device.


## -parameters




### -param InitiatingInstance [in]

Opaque instance pointer for the minifilter driver instance that is initiating the read request. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

Pointer to a file object for the file that the data is to be read from. This file object must be currently open. Calling <b>FltReadFile</b> when the file object is not yet open or is no longer open (for example, in a pre-create or post-cleanup callback routine) causes the system to ASSERT on a checked build. This parameter is required and cannot be <b>NULL</b>. 


### -param ByteOffset [in, optional]

Pointer to a caller-allocated variable that specifies the starting byte offset within the file where the read operation is to begin. 

If this offset is supplied, or if the FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET flag is specified in the <i>Flags</i> parameter, <b>FltReadFile</b> does not update the file object's <b>CurrentByteOffset</b> field. 

If the file object that <i>FileObject</i> points to was opened for synchronous I/O, the caller of <b>FltReadFile</b> can specify that the current file position offset be used instead of an explicit <i>ByteOffset</i> value by setting this parameter to <b>NULL</b>. If the current file position is used, <b>FltReadFile</b> updates the file object's <b>CurrentByteOffset</b> field by adding the number of bytes read when it completes the read operation. 

If the file object that <i>FileObject</i> points to was opened for asynchronous I/O, this parameter is required and cannot be <b>NULL</b>. 


### -param Length [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the data that is read from the file. 


### -param Flags [in]

Bitmask of flags specifying the type of read operation to be performed. 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET

</td>
<td>
Minifilter drivers can set this flag to specify that <b>FltReadFile</b> should not update the file object's <b>CurrentByteOffset</b> field. 

</td>
</tr>
<tr>
<td>
FLTFL_IO_OPERATION_NON_CACHED

</td>
<td>
Minifilter drivers can set this flag to specify a noncached read, even if the file object was not opened with FILE_NO_INTERMEDIATE_BUFFERING. 

</td>
</tr>
<tr>
<td>
FLTFL_IO_OPERATION_PAGING

</td>
<td>
Minifilter drivers can set this flag to specify a paging read. 

</td>
</tr>
<tr>
<td>
FLTFL_IO_OPERATION_SYNCHRONOUS_PAGING

</td>
<td>
Minifilter drivers can set this flag to specify a synchronous paging I/O read. Minifilter drivers that set this flag must also set the FLTFL_IO_OPERATION_PAGING flag.

This flag is available for Windows Vista and later versions of the Windows operating system.


</td>
</tr>
</table>
 


### -param BytesRead [out, optional]

Pointer to a caller-allocated variable that receives the number of bytes read from the file. If <i>CallbackRoutine</i> is not <b>NULL</b>, this parameter is ignored. Otherwise, this parameter is optional and can be <b>NULL</b>. 


### -param CallbackRoutine [in, optional]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_completed_async_io_callback">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>-typed callback routine to call when the read operation is complete. This parameter is optional and can be <b>NULL</b>. 


### -param CallbackContext [in, optional]

Context pointer to be passed to the <i>CallbackRoutine</i> if one is present. This parameter is optional and can be <b>NULL</b>. If <i>CallbackRoutine</i> is <b>NULL</b>, this parameter is ignored. 


## -returns



<b>FltReadFile</b> returns the NTSTATUS value that was returned by the file system. 




## -remarks



A minifilter driver calls <b>FltReadFile</b> to read data from an open file. 

<b>FltReadFile</b> creates a read request and sends it to the minifilter driver instances attached below the initiating instance, and to the file system. The specified instance and the instances attached above it do not receive the read request. 

<b>FltReadFile</b> performs noncached I/O if either of the following is true: 

<ul>
<li>
The caller set the FLTFL_IO_OPERATION_NON_CACHED flag in the <i>Flags</i> parameter. 

</li>
<li>
The file object was opened for noncached I/O. Usually, this is done by specifying the FILE_NO_INTERMEDIATE_BUFFERING <i>CreateOptions</i> flag in the preceding call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex">FltCreateFileEx</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>. 

</li>
</ul>
Noncached I/O imposes the following restrictions on the parameter values passed to <b>FltReadFile</b>: 

<ul>
<li>
The buffer that the <i>Buffer</i> parameter points to must be aligned in accordance with the alignment requirement of the underlying storage device. To allocate such an aligned buffer, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatepoolalignedwithtag">FltAllocatePoolAlignedWithTag</a>. 

</li>
<li>
The byte offset that the <i>ByteOffset</i> parameter points to must be a nonnegative multiple of the volume's sector size. 

</li>
<li>
The length specified in the <i>Length</i> parameter must be a nonnegative multiple of the volume's sector size. 

</li>
</ul>
If an attempt is made to read beyond the end of the file, <b>FltReadFile</b> returns an error. 

If the value of the <i>CallbackRoutine</i> parameter is not <b>NULL</b>, the read operation is performed asynchronously. 

If the value of the <i>CallbackRoutine</i> parameter is <b>NULL</b>, the read operation is performed synchronously. That is, <b>FltReadFile</b> waits until the read operation is complete before returning. This is true even if the file object that <i>FileObject</i> points to was opened for asynchronous I/O. 

If multiple threads call <b>FltReadFile</b> for the same file object, and the file object was opened for synchronous I/O, the Filter Manager does not attempt to serialize I/O on the file. In this respect, <b>FltReadFile</b> differs from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntreadfile">ZwReadFile</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatepoolalignedwithtag">FltAllocatePoolAlignedWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex">FltCreateFileEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_completed_async_io_callback">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntreadfile">ZwReadFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntwritefile">ZwWriteFile</a>
 

 

