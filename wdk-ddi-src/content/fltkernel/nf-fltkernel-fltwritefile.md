---
UID: NF:fltkernel.FltWriteFile
title: FltWriteFile function
author: windows-driver-content
description: FltWriteFile is used to write data to an open file, stream, or device.
old-location: ifsk\fltwritefile.htm
old-project: ifsk
ms.assetid: 994b4a75-4581-423b-8b8f-17a64600fb74
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltWriteFile, ifsk.fltwritefile, FltWriteFile function [Installable File System Drivers], fltkernel/FltWriteFile, FltApiRef_p_to_z_8d4d2b16-fa86-4084-8dad-879d4908f2fe.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltWriteFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltWriteFile function


## -description


<b>FltWriteFile</b> is used to write data to an open file, stream, or device.


## -syntax


````
NTSTATUS FltWriteFile(
  _In_      PFLT_INSTANCE                    InitiatingInstance,
  _In_      PFILE_OBJECT                     FileObject,
  _In_opt_  PLARGE_INTEGER                   ByteOffset,
  _In_      ULONG                            Length,
  _In_      PVOID                            Buffer,
  _In_      FLT_IO_OPERATION_FLAGS           Flags,
  _Out_opt_ PULONG                           BytesWritten,
  _In_opt_  PFLT_COMPLETED_ASYNC_IO_CALLBACK CallbackRoutine,
  _In_opt_  PVOID                            CallbackContext
);
````


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

Pointer to a buffer that contains the data to be written to the file. If the file is opened for noncached I/O, this buffer be must be aligned in accordance with the alignment requirement of the underlying storage device. Minifilter drivers can allocate such an aligned buffer by calling <a href="..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md">FltAllocatePoolAlignedWithTag</a>. 


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

Pointer to a <a href="..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>-typed callback routine to call when the write operation is complete. This parameter is optional and can be <b>NULL</b>. 


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
The file object was opened for noncached I/O. Usually, this is done by specifying the FILE_NO_INTERMEDIATE_BUFFERING <b>CreateOptions</b> flag in the preceding call to <a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>, <a href="..\fltkernel\nf-fltkernel-fltcreatefileex.md">FltCreateFileEx</a>, or <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>. 

</li>
</ul>Noncached I/O imposes the following restrictions on the parameter values passed to <b>FltWriteFile</b>: 
<ul>
<li>
The buffer that the <i>Buffer</i> parameter points to must be aligned in accordance with the alignment requirement of the underlying storage device. To allocate such an aligned buffer, call <a href="..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md">FltAllocatePoolAlignedWithTag</a>. 

</li>
<li>
The byte offset that the <i>ByteOffset</i> parameter points to must be a nonnegative multiple of the volume's sector size. 

</li>
<li>
The length specified in the <i>Length</i> parameter must be a nonnegative multiple of the volume's sector size. 

</li>
</ul>If the value of the <i>CallbackRoutine</i> parameter is not <b>NULL</b>, the write operation is performed asynchronously. 

If the value of the <i>CallbackRoutine</i> parameter is <b>NULL</b>, the write operation is performed synchronously. That is, <b>FltWriteFile</b> waits until the write operation is complete before returning. This is true even if the file object that <i>FileObject</i> points to was opened for asynchronous I/O. 

If multiple threads call <b>FltWriteFile</b> for the same file object, and the file object was opened for synchronous I/O, the Filter Manager does not attempt to serialize I/O on the file. In this respect, <b>FltWriteFile</b> differs from <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>. 



## -see-also

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex.md">FltCreateFileEx</a>

<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>

<a href="..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md">FltAllocatePoolAlignedWithTag</a>

<a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a>

<a href="..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>

<a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltWriteFile function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

