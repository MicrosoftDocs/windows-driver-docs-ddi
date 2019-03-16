---
UID: NF:fltkernel.FltWriteFile
title: FltWriteFile function (fltkernel.h)
description: FltWriteFile is used to write data to an open file, stream, or device.
old-location: ifsk\fltwritefile.htm
tech.root: ifsk
ms.assetid: 994b4a75-4581-423b-8b8f-17a64600fb74
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_8d4d2b16-fa86-4084-8dad-879d4908f2fe.xml, FltWriteFile, FltWriteFile function [Installable File System Drivers], fltkernel/FltWriteFile, ifsk.fltwritefile
ms.topic: function
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
- FltWriteFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltWriteFile function


## -description


<b>FltWriteFile</b> is used to write data to an open file, stream, or device.


## -parameters




### -param InitiatingInstance [in]

Opaque instance pointer for the minifilter driver instance that is initiating the write request. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

Pointer to a file object for the file that the data is to be written to. This file object must be currently open. Calling <b>FltWriteFile</b> when the file object is not yet open or is no longer open (for example, in a pre-create or post-cleanup callback routine) causes the system to ASSERT on a checked build. This parameter is required and cannot be <b>NULL</b>. 


### -param ByteOffset [in, optional]

Pointer to a caller-allocated variable that specifies the starting byte offset within the file where the write operation is to begin. 

If this offset is supplied, or if the FLTFL_IO_OPERATION_DO_NOT_UPDATE_BYTE_OFFSET flag is specified in the <i>Flags</i> parameter, <b>FltWriteFile</b> does not update the file object's <b>CurrentByteOffset</b> field. 

If the file object that <i>FileObject</i> points to was opened for synchronous I/O, the caller of <b>FltWriteFile</b> can specify that the current file position offset be used instead of an explicit <i>ByteOffset</i> value by setting this parameter to <b>NULL</b>. If the current file position is used, <b>FltWriteFile</b> updates the file object's <b>CurrentByteOffset</b> field by adding the number of bytes written when it completes the write operation. 

If the file object that <i>FileObject</i> points to was opened for asynchronous I/O, this parameter is required and cannot be <b>NULL</b>. 


<div class="alert"><b>Note</b>  Prior to Windows 8, the special constants FILE_WRITE_TO_END_OF_FILE and  FILE_USE_FILE_POINTER_POSITION are not supported for this parameter.</div>
<div> </div>



### -param Length [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. 


### -param Buffer [in]

Pointer to a buffer that contains the data to be written to the file. If the file is opened for noncached I/O, this buffer be must be aligned in accordance with the alignment requirement of the underlying storage device. Minifilter drivers can allocate such an aligned buffer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541762">FltAllocatePoolAlignedWithTag</a>. 


### -param Flags [in]

Bitmask of flags specifying the type of write operation to be performed. 

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
Minifilter drivers can set this flag to specify that <b>FltWriteFile</b> should not update the file object's <b>CurrentByteOffset</b> field. 

</td>
</tr>
<tr>
<td>
FLTFL_IO_OPERATION_NON_CACHED

</td>
<td>
Minifilter drivers can set this flag to specify a noncached write, even if the file object was not opened with FILE_NO_INTERMEDIATE_BUFFERING. 

</td>
</tr>
<tr>
<td>
FLTFL_IO_OPERATION_PAGING

</td>
<td>
Minifilter drivers can set this flag to specify a paging write. 

</td>
</tr>
<tr>
<td>
FLTFL_IO_OPERATION_SYNCHRONOUS_PAGING

</td>
<td>
Minifilter drivers can set this flag to specify a synchronous paging I/O write. Minifilter drivers that set this flag must also set the FLTFL_IO_OPERATION_PAGING flag.

This flag is available for Windows Vista and later versions of the Windows operating system.


</td>
</tr>
</table>
 


### -param BytesWritten [out, optional]

Pointer to a caller-allocated variable that receives the number of bytes written to the file. If <i>CallbackRoutine</i> is not <b>NULL</b>, this parameter is ignored. Otherwise, this parameter is optional and can be <b>NULL</b>. 


### -param CallbackRoutine [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551067">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>-typed callback routine to call when the write operation is complete. This parameter is optional and can be <b>NULL</b>. 


### -param CallbackContext [in, optional]

Context pointer to be passed to the <i>CallbackRoutine</i> if one is present. This parameter is optional and can be <b>NULL</b>. If <i>CallbackRoutine</i> is <b>NULL</b>, this parameter is ignored. 


## -returns



<b>FltWriteFile</b> returns the NTSTATUS value that was returned by the file system. 




## -remarks



A minifilter driver calls <b>FltWriteFile</b> to write data to an open file. 

<b>FltWriteFile</b> causes a write request to be sent to the minifilter driver instances attached below the initiating instance and to the file system. The specified instance and the instances attached above it do not receive the write request. 

<b>FltWriteFile</b> performs noncached I/O if either of the following is true: 

<ul>
<li>
The caller set the FLTFL_IO_OPERATION_NON_CACHED flag in the <i>Flags</i> parameter. 

</li>
<li>
The file object was opened for noncached I/O. Usually, this is done by specifying the FILE_NO_INTERMEDIATE_BUFFERING <b>CreateOptions</b> flag in the preceding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541937">FltCreateFileEx</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>. 

</li>
</ul>
Noncached I/O imposes the following restrictions on the parameter values passed to <b>FltWriteFile</b>: 

<ul>
<li>
The buffer that the <i>Buffer</i> parameter points to must be aligned in accordance with the alignment requirement of the underlying storage device. To allocate such an aligned buffer, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541762">FltAllocatePoolAlignedWithTag</a>. 

</li>
<li>
The byte offset that the <i>ByteOffset</i> parameter points to must be a nonnegative multiple of the volume's sector size. 

</li>
<li>
The length specified in the <i>Length</i> parameter must be a nonnegative multiple of the volume's sector size. 

</li>
</ul>
If the value of the <i>CallbackRoutine</i> parameter is not <b>NULL</b>, the write operation is performed asynchronously. 

If the value of the <i>CallbackRoutine</i> parameter is <b>NULL</b>, the write operation is performed synchronously. That is, <b>FltWriteFile</b> waits until the write operation is complete before returning. This is true even if the file object that <i>FileObject</i> points to was opened for asynchronous I/O. 

If multiple threads call <b>FltWriteFile</b> for the same file object, and the file object was opened for synchronous I/O, the Filter Manager does not attempt to serialize I/O on the file. In this respect, <b>FltWriteFile</b> differs from <a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541762">FltAllocatePoolAlignedWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541937">FltCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544286">FltReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551067">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a>
 

 

