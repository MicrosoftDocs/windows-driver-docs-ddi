---
UID: NF:fltkernel.FltPerformAsynchronousIo
title: FltPerformAsynchronousIo function
author: windows-driver-content
description: A minifilter driver calls FltPerformAsynchronousIo to initiate an asynchronous I/O operation.
old-location: ifsk\fltperformasynchronousio.htm
old-project: ifsk
ms.assetid: c76529fe-c808-4239-9bde-68dc68d987ec
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fltkernel/FltPerformAsynchronousIo, FltPerformAsynchronousIo, ifsk.fltperformasynchronousio, FltPerformAsynchronousIo function [Installable File System Drivers], FltApiRef_p_to_z_ed6cd087-6139-4280-aaf3-fe6f0d5b056a.xml
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltPerformAsynchronousIo
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltPerformAsynchronousIo function


## -description


A minifilter driver calls <b>FltPerformAsynchronousIo</b> to initiate an asynchronous I/O operation. 


## -syntax


````
NTSTATUS FltPerformAsynchronousIo(
  _Inout_ PFLT_CALLBACK_DATA               CallbackData,
  _In_    PFLT_COMPLETED_ASYNC_IO_CALLBACK CallbackRoutine,
  _In_    PVOID                            CallbackContext
);
````


## -parameters




### -param CallbackData [in, out]

Pointer to a callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure allocated by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>. This parameter is required and cannot be <b>NULL</b>. The caller is responsible for freeing this structure when it is no longer needed by calling <a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a>. 


### -param CallbackRoutine [in]

Pointer to a <a href="..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>-typed callback routine to be called when the I/O operation is completed. Note: The Filter Manager calls this routine after it calls the postoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routines of any minifilter drivers whose instances are attached below the initiating instance (specified in the <i>Instance</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>). This parameter is required and cannot be <b>NULL</b>. The Filter Manager always calls this routine, even when <b>FltPerformAsynchronousIo</b> fails. 


### -param CallbackContext [in]

Context pointer to be passed to the <i>CallbackRoutine</i> This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltPerformAsynchronousIo</b> returns STATUS_SUCCESS to indicate that the I/O operation is complete, and the callback routine that <i>CallbackRoutine</i> points to has been called. Otherwise, it returns an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INVALID_ASYNCHRONOUS_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
IRP_MJ_CREATE requests cannot be performed asynchronously. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The operation returned STATUS_PENDING. The callback routine that <i>CallbackRoutine</i> points to is called when the I/O operation is complete. This is a success code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver calls <b>FltPerformAsynchronousIo</b> to initiate an asynchronous I/O operation after calling <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a> to allocate a callback data structure for the operation. 

<b>FltPerformAsynchronousIo</b> sends the I/O operation only to the minifilter driver instances attached below the initiating instance (specified in the <i>Instance</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>), and the file system. Minifilter drivers attached above the specified instance do not receive the I/O operation. 

Minifilter drivers can only initiate IRP-based I/O operations. They cannot initiate fast I/O or file system filter (FSFilter) callback operations. 

Minifilter drivers should use <b>FltPerformAsynchronousIo</b> only for asynchronous I/O operations for which routines such as the following cannot be used: 


<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>


IRP_MJ_CREATE requests cannot be performed asynchronously. 

The callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure can be freed or reused at any time after the callback routine that <i>CallbackRoutine</i> points to has been called. The caller can free the callback data structure by calling <a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a> or prepare it for reuse by calling <a href="..\fltkernel\nf-fltkernel-fltreusecallbackdata.md">FltReuseCallbackData</a>. Because the callback routine that <i>CallbackRoutine</i> points to is always called by the Filter Manager, even when <b>FltPerformAsynchronousIo</b> fails, the minifilter driver can perform the freeing or reusing operations directly in the callback routine.

Note that the NTSTATUS value returned by <b>FltPerformAsynchronousIo</b> indicates only whether the I/O operation was successfully initiated. This is not the same as the final status of the I/O operation. To determine the status returned by the underlying minifilter drivers, filter drivers, and file system for the operation, the <i>CallbackRoutine</i> should examine the <b>IoStatus</b> member of the callback data structure received in the <i>CallbackRoutine</i>'s <i>CallbackContext</i> parameter. 

The caller of <b>FltPerformAsynchronousIo</b> can be running at IRQL &lt;= APC_LEVEL if the IRP_PAGING_IO flag is set in the <b>IrpFlags</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md">FLT_IO_PARAMETER_BLOCK</a> structure for the operation. (This flag is only valid for IRP_MJ_READ, IRP_MJ_WRITE, IRP_MJ_QUERY_INFORMATION, and IRP_MJ_SET_INFORMATION operations.) Otherwise, the caller must be running at IRQL PASSIVE_LEVEL. 




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltreusecallbackdata.md">FltReuseCallbackData</a>



<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltperformsynchronousio.md">FltPerformSynchronousIo</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltPerformAsynchronousIo function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

