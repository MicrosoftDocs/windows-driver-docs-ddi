---
UID: NF:fltkernel.FltRequestOperationStatusCallback
title: FltRequestOperationStatusCallback function
author: windows-driver-content
description: FltRequestOperationStatusCallback returns status information for the given I/O operation.
old-location: ifsk\fltrequestoperationstatuscallback.htm
old-project: ifsk
ms.assetid: 17379ce3-d9c1-4fbf-ab2e-b87604e6c71e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltRequestOperationStatusCallback
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
req.alt-api: FltRequestOperationStatusCallback
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
req.typenames: EXpsFontRestriction
---

# FltRequestOperationStatusCallback function



## -description
<b>FltRequestOperationStatusCallback</b> returns status information for the given I/O operation. 



## -syntax

````
NTSTATUS FltRequestOperationStatusCallback(
  _In_     PFLT_CALLBACK_DATA                 Data,
  _In_     PFLT_GET_OPERATION_STATUS_CALLBACK CallbackRoutine,
  _In_opt_ PVOID                              RequesterContext
);
````


## -parameters

### -param Data [in]

A pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


### -param CallbackRoutine [in]

A pointer to a callback routine that the Filter Manager calls after <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> returns. This parameter is required and cannot be <b>NULL</b>. 


### -param RequesterContext [in, optional]

A context pointer to be passed to the <i>CallbackRoutine</i>. This parameter is optional and can be <b>NULL</b>. 


## -returns
<b>FltRequestOperationStatusCallback</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The minifilter driver's instance is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><b>FltRequestOperationStatusCallback</b> encountered a pool allocation failure. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><b>FltRequestOperationStatusCallback</b> was called from a routine that was not a preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine, or the I/O operation was an IRP_MJ_CLOSE request. This is an error code. 

 


## -remarks
A minifilter driver can call <b>FltRequestOperationStatusCallback</b> for an IRP-based I/O operation to obtain the status value that <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> returned for the operation. 

Most minifilter drivers never need to call <b>FltRequestOperationStatusCallback</b>. Normally, a minifilter driver only calls this routine to determine whether a requested oplock was granted. 

<b>FltRequestOperationStatusCallback</b> can only be called from a minifilter driver's preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine. 

<b>FltRequestOperationStatusCallback</b> can only be called for non-IRP_MJ_CLOSE IRP-based operations. To determine whether the operation is an IRP-based operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro.

If the IRP-based operation is an IRP_MJ_CLOSE request, STATUS_INVALID_PARAMETER is returned.

<b>FltRequestOperationStatusCallback</b> copies the contents of the I/O parameter block (<a href="..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md">FLT_IO_PARAMETER_BLOCK</a>) to the <b>Iopb</b> member of the callback data (FLT_CALLBACK_DATA), and this is the callback data that the Filter Manager will pass to the routine specified in the <i>CallbackRoutine</i> parameter. The copied data represents a snapshot of the I/O parameter block at the time that the preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine calls <b>FltRequestOperationStatusCallback</b>. If the preoperation callback routine changes the I/O parameter block after calling <b>FltRequestOperationStatusCallback</b>, the I/O parameter block that the Filter Manager passes to <i>CallbackRoutine</i> will be different from the I/O parameter block that the filter driver passes down the driver stack when it calls <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>.

The following example code from a preoperation callback routine illustrates how this might happen:

In the example, the read buffer is changed after the call to <b>FltRequestOperationStatusCallback</b>, so when the Filter Manager calls <i>CallbackRoutine</i>, it will pass in a pointer to the old buffer instead of the new one. 

The Filter Manager calls the given <i>CallbackRoutine</i> in the context of the originating thread at IRQL &lt;= APC_LEVEL. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md">FLT_IO_PARAMETER_BLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_get_operation_status_callback.md">PFLT_GET_OPERATION_STATUS_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltRequestOperationStatusCallback function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

