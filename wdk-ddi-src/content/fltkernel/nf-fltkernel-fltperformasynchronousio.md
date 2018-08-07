---
UID: NF:fltkernel.FltPerformAsynchronousIo
title: FltPerformAsynchronousIo function
author: windows-driver-content
description: A minifilter driver calls FltPerformAsynchronousIo to initiate an asynchronous I/O operation.
old-location: ifsk\fltperformasynchronousio.htm
tech.root: ifsk
ms.assetid: c76529fe-c808-4239-9bde-68dc68d987ec
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_p_to_z_ed6cd087-6139-4280-aaf3-fe6f0d5b056a.xml, FltPerformAsynchronousIo, FltPerformAsynchronousIo function [Installable File System Drivers], fltkernel/FltPerformAsynchronousIo, ifsk.fltperformasynchronousio
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltPerformAsynchronousIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltPerformAsynchronousIo function


## -description


A minifilter driver calls <b>FltPerformAsynchronousIo</b> to initiate an asynchronous I/O operation. 


## -parameters




### -param CallbackData [in, out]

Pointer to a callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure allocated by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a>. This parameter is required and cannot be <b>NULL</b>. The caller is responsible for freeing this structure when it is no longer needed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff542949">FltFreeCallbackData</a>. 


### -param CallbackRoutine [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551067">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>-typed callback routine to be called when the I/O operation is completed. Note: The Filter Manager calls this routine after it calls the postoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) routines of any minifilter drivers whose instances are attached below the initiating instance (specified in the <i>Instance</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a>). This parameter is required and cannot be <b>NULL</b>. The Filter Manager always calls this routine, even when <b>FltPerformAsynchronousIo</b> fails. 


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



A minifilter driver calls <b>FltPerformAsynchronousIo</b> to initiate an asynchronous I/O operation after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a> to allocate a callback data structure for the operation. 

<b>FltPerformAsynchronousIo</b> sends the I/O operation only to the minifilter driver instances attached below the initiating instance (specified in the <i>Instance</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a>), and the file system. Minifilter drivers attached above the specified instance do not receive the I/O operation. 

Minifilter drivers can only initiate IRP-based I/O operations. They cannot initiate fast I/O or file system filter (FSFilter) callback operations. 

Minifilter drivers should use <b>FltPerformAsynchronousIo</b> only for asynchronous I/O operations for which routines such as the following cannot be used: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544286">FltReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544610">FltWriteFile</a>


IRP_MJ_CREATE requests cannot be performed asynchronously. 

The callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure can be freed or reused at any time after the callback routine that <i>CallbackRoutine</i> points to has been called. The caller can free the callback data structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff542949">FltFreeCallbackData</a> or prepare it for reuse by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544358">FltReuseCallbackData</a>. Because the callback routine that <i>CallbackRoutine</i> points to is always called by the Filter Manager, even when <b>FltPerformAsynchronousIo</b> fails, the minifilter driver can perform the freeing or reusing operations directly in the callback routine.

Note that the NTSTATUS value returned by <b>FltPerformAsynchronousIo</b> indicates only whether the I/O operation was successfully initiated. This is not the same as the final status of the I/O operation. To determine the status returned by the underlying minifilter drivers, filter drivers, and file system for the operation, the <i>CallbackRoutine</i> should examine the <b>IoStatus</b> member of the callback data structure received in the <i>CallbackRoutine</i>'s <i>CallbackContext</i> parameter. 

The caller of <b>FltPerformAsynchronousIo</b> can be running at IRQL &lt;= APC_LEVEL if the IRP_PAGING_IO flag is set in the <b>IrpFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544638">FLT_IO_PARAMETER_BLOCK</a> structure for the operation. (This flag is only valid for IRP_MJ_READ, IRP_MJ_WRITE, IRP_MJ_QUERY_INFORMATION, and IRP_MJ_SET_INFORMATION operations.) Otherwise, the caller must be running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544638">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542949">FltFreeCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543421">FltPerformSynchronousIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544358">FltReuseCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551067">PFLT_COMPLETED_ASYNC_IO_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>
 

 

