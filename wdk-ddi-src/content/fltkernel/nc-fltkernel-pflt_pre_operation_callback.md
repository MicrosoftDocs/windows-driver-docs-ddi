---
UID: NC:fltkernel.PFLT_PRE_OPERATION_CALLBACK
title: PFLT_PRE_OPERATION_CALLBACK
author: windows-driver-content
description: A minifilter driver's PFLT_PRE_OPERATION_CALLBACK routine performs pre-operation processing for I/O operations.
old-location: ifsk\pflt_pre_operation_callback.htm
old-project: ifsk
ms.assetid: 758a480a-b52c-45e4-8c78-74c805c61e07
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltCallbacks_cfde61cc-2054-4263-8697-aa50a1c9d267.xml, PFLT_PRE_OPERATION_CALLBACK, PFLT_PRE_OPERATION_CALLBACK function pointer [Installable File System Drivers], fltkernel/PFLT_PRE_OPERATION_CALLBACK, ifsk.pflt_pre_operation_callback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later Windows operating systems.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fltkernel.h
api_name:
-	PFLT_PRE_OPERATION_CALLBACK
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_PRE_OPERATION_CALLBACK callback


## -description


A minifilter driver's PFLT_PRE_OPERATION_CALLBACK routine performs pre-operation processing for I/O operations. 


## -prototype


````
typedef FLT_PREOP_CALLBACK_STATUS ( *PFLT_PRE_OPERATION_CALLBACK)(
  _Inout_ PFLT_CALLBACK_DATA    Data,
  _In_    PCFLT_RELATED_OBJECTS FltObjects,
  _Out_   PVOID                 *CompletionContext
);
````


## -parameters




### -param Data [in, out]

A pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


### -param FltObjects [in]

A pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current I/O request. 


### -param *CompletionContext [out]

If this callback routine returns FLT_PREOP_SUCCESS_WITH_CALLBACK or FLT_PREOP_SYNCHRONIZE, this parameter is an optional context pointer to be passed to the corresponding post-operation callback routine. Otherwise, it must be <b>NULL</b>. 


## -returns



This callback routine returns one of the following FLT_PREOP_CALLBACK_STATUS values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_COMPLETE</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver is completing the I/O operation. The filter manager does not send the I/O operation to any minifilter drivers below the caller in the driver stack or to the file system. In this case, the filter manager only calls the post-operation callback routines of the minifilter drivers above the caller in the driver stack. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_DISALLOW_FASTIO</b></dt>
</dl>
</td>
<td width="60%">
The operation is a fast I/O operation, and the minifilter driver is not allowing the fast I/O path to be used for this operation. The filter manager does not send the fast I/O operation to any minifilter drivers below the caller in the driver stack or to the file system. In this case, the filter manager only calls the post-operation callback routines of the minifilter drivers above the caller in the driver stack. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver has pended the I/O operation, and the operation is still pending. The filter manager does not process the I/O operation further until the minifilter driver calls <a href="..\fltkernel\nf-fltkernel-fltcompletependedpreoperation.md">FltCompletePendedPreOperation</a>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_SUCCESS_NO_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver is returning the I/O operation to the filter manager for further processing. In this case, the filter manager does not call the minifilter driver's post-operation callback, if one exists, during I/O completion. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_SUCCESS_WITH_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver is returning the I/O operation to the filter manager for further processing. In this case, the filter manager calls the minifilter driver's post-operation callback during I/O completion. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_SYNCHRONIZE</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver is returning the I/O operation to the filter manager for further processing, but it is not completing the operation. In this case, the filter manager calls the minifilter's post-operation callback in the context of the current thread at IRQL &lt;= APC_LEVEL. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver's pre-operation callback routine processes one or more types of I/O operations. This callback routine is similar to a dispatch routine in the legacy filter model. 

A minifilter driver registers a pre-operation callback routine for a particular type of I/O operation by storing the callback routine's entry point in the <b>OperationRegistration</b> array of the <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> structure. The minifilter driver passes this structure as a parameter to <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> in its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine. A minifilter driver can register a pre-operation callback routine for a given type of I/O operation without registering a post-operation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routine and vice versa. 

If this routine returns FLT_PREOP_COMPLETE, it must set the callback data structure's <b>IoStatus.Status</b> field to the final NTSTATUS value for the I/O operation. This NTSTATUS value cannot be STATUS_PENDING. For a cleanup or close operation, it must be a success NTSTATUS value other than STATUS_PENDING because cleanup and close operations cannot fail. 

If this routine returns FLT_PREOP_DISALLOW_FASTIO, it should not set the callback data structure's <b>IoStatus.Status</b> field because the filter manager automatically sets this field to STATUS_FLT_DISALLOW_FAST_IO. 

FLT_PREOP_DISALLOW_FASTIO can only be returned for a fast I/O operation. To determine whether a given callback data structure represents a fast I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544645">FLT_IS_FASTIO_OPERATION</a> macro. 

FLT_PREOP_PENDING can only be returned for IRP-based I/O operations because only IRP-based I/O operations can be pended. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

If a minifilter driver's pre-operation callback routine returns FLT_PREOP_SYNCHRONIZE, the minifilter driver must have registered a corresponding post-operation callback for the operation. 

FLT_PREOP_SYNCHRONIZE should only be returned for IRP-based I/O operations. If it is returned for an I/O operation that is not an IRP-based operation, the filter manager treats this return value as if it were FLT_PREOP_SUCCESS_WITH_CALLBACK. 

Minifilter drivers should not return FLT_PREOP_SYNCHRONIZE for create operations, because these operations are already synchronized by the filter manager. 

Minifilter drivers must never return FLT_PREOP_SYNCHRONIZE for asynchronous read and write operations. Doing so can severely degrade both minifilter driver and system performance. 

A minifilter driver's pre-operation or post-operation callback routine can modify the contents of the callback data structure for the operation. If it does, it must then call <a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>, unless it has changed the contents of the callback data structure's <b>IoStatus</b> field. 

The IRQL for this generic callback routine depends on its specific IO paths.

File systems round write and read operations at end of file up to a multiple of the sector size of the underlying file storage device. When processing pre-read or pre-write operations, filters that allocate and swap buffers need to round the size of an allocated buffer up to a multiple of the sector size of the associated device. If they do not, the length of data transferred from the underlying file system will exceed the allocated length of the buffer. For more information about swapping buffers, see <a href="http://go.microsoft.com/fwlink/p/?linkid=256055">swapBuffers Minifilter Sample</a>.

Starting with Windows 8, <i>CompletionContext</i> uses the <a href="https://msdn.microsoft.com/C3B285EA-0DAB-48D4-AE2F-CB4FBB30EF15">_Flt_CompletionContext_Outptr_</a> annotation which defines valid context values based on the operation result. The following is a usage example for the callback with the annotation for <i>CompletionContext</i>.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>FLT_PREOP_CALLBACK_STATUS 
SwapPreReadBuffers( 
    _Inout_ PFLT_CALLBACK_DATA Data, 
    _In_ PCFLT_RELATED_OBJECTS FltObjects, 
    _Flt_CompletionContext_Outptr_ PVOID *CompletionContext 
    ); 
  
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a>



<a href="..\fltkernel\nf-fltkernel-fltqueuedeferredioworkitem.md">FltQueueDeferredIoWorkItem</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/C3B285EA-0DAB-48D4-AE2F-CB4FBB30EF15">_Flt_CompletionContext_Outptr_</a>



<a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>



<a href="..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544645">FLT_IS_FASTIO_OPERATION</a>



<a href="..\fltkernel\nf-fltkernel-fltcompletependedpreoperation.md">FltCompletePendedPreOperation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544663">FLT_IS_SYSTEM_BUFFER</a>



<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>



<a href="..\fltkernel\nf-fltkernel-fltcompletependedpostoperation.md">FltCompletePendedPostOperation</a>



<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544660">FLT_IS_REISSUED_IO</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



 

 


