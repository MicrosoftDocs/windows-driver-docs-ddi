---
UID: NS:fltkernel._FLT_IO_PARAMETER_BLOCK
title: "_FLT_IO_PARAMETER_BLOCK"
author: windows-driver-content
description: The FLT_IO_PARAMETER_BLOCK structure contains the parameters for the I/O operation that is represented by a callback data (FLT_CALLBACK_DATA) structure.
old-location: ifsk\flt_io_parameter_block.htm
old-project: ifsk
ms.assetid: a62f6db3-baca-492a-b485-062fcc69f563
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltSystemStructures_8abf39e5-b9d1-4c44-8137-80ee1b35c0a3.xml, PFLT_IO_PARAMETER_BLOCK, *PFLT_IO_PARAMETER_BLOCK, fltkernel/FLT_IO_PARAMETER_BLOCK, _FLT_IO_PARAMETER_BLOCK, PFLT_IO_PARAMETER_BLOCK structure pointer [Installable File System Drivers], FLT_IO_PARAMETER_BLOCK structure [Installable File System Drivers], ifsk.flt_io_parameter_block, FLT_IO_PARAMETER_BLOCK, fltkernel/PFLT_IO_PARAMETER_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltkernel.h
apiname:
-	FLT_IO_PARAMETER_BLOCK
product: Windows
targetos: Windows
req.typenames: FLT_IO_PARAMETER_BLOCK, *PFLT_IO_PARAMETER_BLOCK
---

# _FLT_IO_PARAMETER_BLOCK structure


## -description


The FLT_IO_PARAMETER_BLOCK structure contains the parameters for the I/O operation that is represented by a callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure. 


## -syntax


````
typedef struct _FLT_IO_PARAMETER_BLOCK {
  ULONG          IrpFlags;
  UCHAR          MajorFunction;
  UCHAR          MinorFunction;
  UCHAR          OperationFlags;
  UCHAR          Reserved;
  PFILE_OBJECT   TargetFileObject;
  PFLT_INSTANCE  TargetInstance;
  FLT_PARAMETERS Parameters;
} FLT_IO_PARAMETER_BLOCK, *PFLT_IO_PARAMETER_BLOCK;
````


## -struct-fields




#### - IrpFlags

A bitmask of flags that specify various aspects of the I/O operation. These flags are used only for IRP-based operations. The following table shows flag values. 
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
IRP_BUFFERED_IO

</td>
<td>
The operation is a buffered I/O operation. 

</td>
</tr>
<tr>
<td>
IRP_CLOSE_OPERATION

</td>
<td>
The operation is a cleanup or close operation. 

</td>
</tr>
<tr>
<td>
IRP_DEALLOCATE_BUFFER

</td>
<td>
The I/O Manager will free the buffer during the completion phase for the IRP.

</td>
</tr>
<tr>
<td>
IRP_INPUT_OPERATION

</td>
<td>
The operation is an input operation.

</td>
</tr>
<tr>
<td>
IRP_NOCACHE

</td>
<td>
The operation is a noncached I/O operation.

</td>
</tr>
<tr>
<td>
IRP_PAGING_IO

</td>
<td>
The operation is a paging I/O operation.

</td>
</tr>
<tr>
<td>
IRP_SYNCHRONOUS_API

</td>
<td>
The I/O operation is synchronous.

</td>
</tr>
<tr>
<td>
IRP_SYNCHRONOUS_PAGING_IO

</td>
<td>
The operation is a synchronous paging I/O operation.

</td>
</tr>
<tr>
<td>
IRP_MOUNT_COMPLETION

</td>
<td>
A volume mount  is completed for the operation. 

</td>
</tr>
<tr>
<td>
IRP_CREATE_OPERATION

</td>
<td>
The operation is a create or open operation. 

</td>
</tr>
<tr>
<td>
IRP_READ_OPERATION

</td>
<td>
The I/O operation is for reading.

</td>
</tr>
<tr>
<td>
IRP_WRITE_OPERATION

</td>
<td>
The I/O operation is for writing.

</td>
</tr>
<tr>
<td>
IRP_DEFER_IO_COMPLETION

</td>
<td>
I/O Completion of the operation is deferred.

</td>
</tr>
<tr>
<td>
IRP_ASSOCIATED_IRP

</td>
<td>
The operation is associated with a master IRP.

</td>
</tr>
<tr>
<td>
IRP_OB_QUERY_NAME

</td>
<td>
The operation is an asynchronous name query.

</td>
</tr>
<tr>
<td>
IRP_HOLD_DEVICE_QUEUE

</td>
<td>
Reserved.

</td>
</tr>
<tr>
<td>
IRP_UM_DRIVER_INITIATED_IO

</td>
<td>
The operation originated from a user mode driver.

</td>
</tr>
</table> 


#### - MajorFunction

The major function code for the I/O operation. Major function codes are used for IRP-based operations, fast I/O operations, and file system (FSFilter) callback operations. For more information about additional operations, see <a href="..\fltkernel\ns-fltkernel-_flt_parameters.md">FLT_PARAMETERS</a>.


#### - MinorFunction

The minor function code for the I/O operation. This member is optional and can be <b>NULL</b>. The value of the <b>MajorFunction</b> member determines the possible values. For more information about minor function codes, see <a href="..\fltkernel\ns-fltkernel-_flt_parameters.md">FLT_PARAMETERS</a>. 


#### - OperationFlags

A bitmask of flags that specify various aspects of the I/O operation. These flags are used only for IRP-based operations. The Filter Manager copies these flags from the  <b>Flags</b> member of the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure that is associated with the <a href="..\wdm\ns-wdm-_irp.md">IRP</a>. The following table shows the most commonly used flag values.
<table>
<tr>
<th>Value</th>
<th>Meaning </th>
</tr>
<tr>
<td>
SL_CASE_SENSITIVE

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>. If this flag is set, file name comparisons should be case-sensitive. 

</td>
</tr>
<tr>
<td>
SL_EXCLUSIVE_LOCK

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>. If this flag is set, an exclusive byte-range lock is requested. Otherwise, a shared lock is requested. 

</td>
</tr>
<tr>
<td>
SL_FAIL_IMMEDIATELY

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>. If this flag is set, the lock request should fail if it cannot be granted immediately. 

</td>
</tr>
<tr>
<td>
SL_FORCE_ACCESS_CHECK

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>. If this flag is set, access checks must be performed even if the value of the IRP's <b>RequestorMode</b> member is <b>KernelMode</b>. 

</td>
</tr>
<tr>
<td>
SL_FORCE_DIRECT_WRITE

</td>
<td>
Used for IRP_MJ_WRITE and IOCTL_DISK_COPY_DATA.  If this flag is set, kernel-mode drivers can write to volume areas that they normally cannot write to because of direct write blocking. Direct write blocking was implemented for security reasons in Windows Vista and later operating systems.  This flag is checked both at the file system layer and storage stack layer.  For more information about this flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551353">Blocking Direct Write Operations to Volumes and Disks</a>. The SL_FORCE_DIRECT_WRITE flag is available in Windows Vista and later versions of Windows.

</td>
</tr>
<tr>
<td>
SL_INDEX_SPECIFIED

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a>. If this flag is set, the scan for directory, quota, or extended-attribute information should begin at the entry in the list whose index is specified. 

</td>
</tr>
<tr>
<td>
SL_OPEN_PAGING_FILE

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>. If this flag is set, the file is a paging file. 

</td>
</tr>
<tr>
<td>
SL_OPEN_TARGET_DIRECTORY

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>. If this flag is set, the file's parent directory should be opened. 

</td>
</tr>
<tr>
<td>
SL_OVERRIDE_VERIFY_VOLUME

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>. If this flag is set, the I/O operation should be performed even if the DO_VERIFY_VOLUME flag is set on the volume's device object. 

</td>
</tr>
<tr>
<td>
SL_RESTART_SCAN

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a>. If this flag is set, the scan for directory, quota, or extended-attribute information should begin at the first entry in the directory or list. Otherwise, the scan should be resumed from the previous scan. 

</td>
</tr>
<tr>
<td>
SL_RETURN_SINGLE_ENTRY

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a>. If this flag is set, the scan for directory, quota, or extended-attribute information should return only the first entry that is found. 

</td>
</tr>
<tr>
<td>
SL_WATCH_TREE

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>. If this flag is set, all subdirectories of this directory should also be watched. Otherwise, only the directory itself is to be watched. 

</td>
</tr>
<tr>
<td>
SL_WRITE_THROUGH

</td>
<td>
Used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>. If this flag is set, the file data must be written through to persistent storage, not just written to the cache. 

</td>
</tr>
</table> 


#### - Reserved

Reserved for system use. Do not use. 


#### - TargetFileObject

A file object pointer for the file or directory that is the target for this I/O operation. 


#### - TargetInstance

An opaque instance pointer for the minifilter that is the target for this I/O operation. 


#### - Parameters

An <a href="..\fltkernel\ns-fltkernel-_flt_parameters.md">FLT_PARAMETERS</a> structure that contains the parameters for the I/O operation that are specified by the <b>MajorFunction</b> and <b>MinorFunction</b> members. 


## -remarks


The FLT_IO_PARAMETER_BLOCK structure contains the parameters for the I/O operation that is represented by a callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure. The callback data structure contains a pointer to the FLT_IO_PARAMETER_BLOCK structure in its  <b>Iopb</b> member. 

A minifilter receives a pointer to the callback data structure as the <i>Data</i> or <i>CallbackData</i> input parameter to the following callback routine types: 


<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_generate_file_name.md">PFLT_GENERATE_FILE_NAME</a>


A minifilter's preoperation and postoperation callback routines can modify the contents of the FLT_IO_PARAMETER_BLOCK structure for the I/O operation, except for the <b>MajorFunction</b> and <b>Reserved</b> members. If it does, it must call <a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>, unless it has also modified the <b>IoStatus</b> member of the callback data structure for the operation. Otherwise, the modified values are ignored. 

If a minifilter's preoperation callback routine modifies the parameters for an I/O operation, all minifilters below it in the minifilter instance stack will receive the modified parameters in their preoperation and postoperation callback routines. 

The modified parameters are not received by the minifilter's own postoperation callback routine, or by any minifilters above that minifilter in the minifilter instance stack. In all cases, a minifilter's preoperation and postoperation callback routines receive the same input parameter values. 

A minifilter can change the value of the <b>TargetInstance</b> member. However, the new value must be a pointer to an instance of the same minifilter at the same altitude on a different volume. In addition, the new volume's device object must have a stack size that is greater than or equal to that of the original volume's device object. 

To get the stack size for a volume device object, given an opaque instance pointer for an instance that is attached to the volume, do the following: 
<ul>
<li>
Call <b>FltGetVolumeFromInstance</b> to get the volume pointer. 

</li>
<li>
Call <b>FltGetDeviceObject</b> to get a pointer to the volume device object. This pointer is returned in the <i>DeviceObject</i> parameter. The device object's stack size can be found in <b>DeviceObject-&gt;StackSize</b>. 

</li>
<li>
When the volume pointer is no longer needed, call <b>FltObjectDereference</b> to decrement its reference count. 

</li>
<li>
When the volume device object pointer is no longer needed, call <b>ObDereferenceObject</b> to decrement its reference count. 

</li>
</ul>A minifilter can change the value of the <b>TargetFileObject</b> member. However, the new value must be a pointer to a file object for a file that resides on the same volume as the instance specified by the <b>TargetInstance</b> member. 

A minifilter cannot safely change the value of the <b>MajorFunction</b> member. Instead, it must initiate a new I/O operation. 

A minifilter can initiate an I/O operation by calling a support routine such as <a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a> or by calling <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a> to allocate a callback data structure; initializing the I/O parameters in the <b>FLT_IO_PARAMETER_BLOCK</b> structure, and passing the callback data structure to <a href="..\fltkernel\nf-fltkernel-fltperformsynchronousio.md">FltPerformSynchronousIo</a> or <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>. <div class="alert"><b>Note</b>  Use support routines wherever possible when initiating I/O operations.  A minifilter should allocate its own callback data only if there is no support function for a particular I/O operation.</div>
<div> </div>




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_parameters.md">FLT_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548608">IRP_MJ_CLEANUP</a>

<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549407">IRP_MJ_SET_SECURITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>

<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a>

<a href="..\fltkernel\nf-fltkernel-fltclearcallbackdatadirty.md">FltClearCallbackDataDirty</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549283">IRP_MJ_QUERY_INFORMATION</a>

<a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549346">IRP_MJ_SET_EA</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>

<a href="..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a>

<a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549415">IRP_MJ_SET_VOLUME_INFORMATION</a>

<a href="..\fltkernel\nc-fltkernel-pflt_generate_file_name.md">PFLT_GENERATE_FILE_NAME</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549268">IRP_MJ_PNP</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549298">IRP_MJ_QUERY_SECURITY</a>

<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a>

<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>

<a href="..\fltkernel\nf-fltkernel-fltiscallbackdatadirty.md">FltIsCallbackDataDirty</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549293">IRP_MJ_QUERY_QUOTA</a>

<a href="..\fltkernel\nf-fltkernel-fltdecodeparameters.md">FltDecodeParameters</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_IO_PARAMETER_BLOCK structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

