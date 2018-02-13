---
UID: NF:fltkernel.FltReadFile
title: FltReadFile function
author: windows-driver-content
description: FltReadFile reads data from an open file, stream, or device.
old-location: ifsk\fltreadfile.htm
old-project: ifsk
ms.assetid: 3ceacb96-1c60-4310-b96f-6fb396c1d6ce
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltApiRef_p_to_z_83c0167c-78df-4692-980b-7a55f531a9db.xml, FltReadFile, FltReadFile function [Installable File System Drivers], ifsk.fltreadfile, fltkernel/FltReadFile
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
-	FltReadFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltReadFile function


## -description


<b>FltReadFile</b> reads data from an open file, stream, or device.


## -syntax


````
NTSTATUS FltReadFile(
  _In_      PFLT_INSTANCE                    InitiatingInstance,
  _In_      PFILE_OBJECT                     FileObject,
  _In_opt_  PLARGE_INTEGER                   ByteOffset,
  _In_      ULONG                            Length,
  _Out_     PVOID                            Buffer,
  _In_      FLT_IO_OPERATION_FLAGS           Flags,
  _Out_opt_ PULONG                           BytesRead,
  _In_opt_  PFLT_COMPLETED_ASYNC_IO_CALLBACK CallbackRoutine,
  _In_opt_  PVOID                            CallbackContext
);
````


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

Pointer to a <a href="..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>-typed callback routine to call when the read operation is complete. This parameter is optional and can be <b>NULL</b>. 


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
The file object was opened for noncached I/O. Usually, this is done by specifying the FILE_NO_INTERMEDIATE_BUFFERING <i>CreateOptions</i> flag in the preceding call to <a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>, <a href="..\fltkernel\nf-fltkernel-fltcreatefileex.md">FltCreateFileEx</a>, or <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>. 

</li>
</ul>
Noncached I/O imposes the following restrictions on the parameter values passed to <b>FltReadFile</b>: 

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
</ul>
If an attempt is made to read beyond the end of the file, <b>FltReadFile</b> returns an error. 

If the value of the <i>CallbackRoutine</i> parameter is not <b>NULL</b>, the read operation is performed asynchronously. 

If the value of the <i>CallbackRoutine</i> parameter is <b>NULL</b>, the read operation is performed synchronously. That is, <b>FltReadFile</b> waits until the read operation is complete before returning. This is true even if the file object that <i>FileObject</i> points to was opened for asynchronous I/O. 

If multiple threads call <b>FltReadFile</b> for the same file object, and the file object was opened for synchronous I/O, the Filter Manager does not attempt to serialize I/O on the file. In this respect, <b>FltReadFile</b> differs from <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>



<a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>



<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md">FltAllocatePoolAlignedWithTag</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex.md">FltCreateFileEx</a>



<a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a>



<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReadFile function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

