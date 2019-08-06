---
UID: NF:fltkernel.FltRequestOperationStatusCallback
title: FltRequestOperationStatusCallback function (fltkernel.h)
description: FltRequestOperationStatusCallback returns status information for the given I/O operation.
old-location: ifsk\fltrequestoperationstatuscallback.htm
tech.root: ifsk
ms.assetid: 17379ce3-d9c1-4fbf-ab2e-b87604e6c71e
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_85d8f6d5-37d1-469f-8c97-8b358f69e9ef.xml, FltRequestOperationStatusCallback, FltRequestOperationStatusCallback function [Installable File System Drivers], fltkernel/FltRequestOperationStatusCallback, ifsk.fltrequestoperationstatuscallback
ms.topic: function
f1_keywords:
 - "fltkernel/FltRequestOperationStatusCallback"
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltRequestOperationStatusCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltRequestOperationStatusCallback function


## -description


<b>FltRequestOperationStatusCallback</b> returns status information for the given I/O operation. 


## -parameters




### -param Data [in]

A pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


### -param CallbackRoutine [in]

A pointer to a callback routine that the Filter Manager calls after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocalldriver">IoCallDriver</a> returns. This parameter is required and cannot be <b>NULL</b>. 


### -param RequesterContext [in, optional]

A context pointer to be passed to the <i>CallbackRoutine</i>. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltRequestOperationStatusCallback</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver's instance is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltRequestOperationStatusCallback</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<b>FltRequestOperationStatusCallback</b> was called from a routine that was not a preoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>) routine, or the I/O operation was an IRP_MJ_CLOSE request. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver can call <b>FltRequestOperationStatusCallback</b> for an IRP-based I/O operation to obtain the status value that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocalldriver">IoCallDriver</a> returned for the operation. 

Most minifilter drivers never need to call <b>FltRequestOperationStatusCallback</b>. Normally, a minifilter driver only calls this routine to determine whether a requested oplock was granted. 

<b>FltRequestOperationStatusCallback</b> can only be called from a minifilter driver's preoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>) routine. 

<b>FltRequestOperationStatusCallback</b> can only be called for non-IRP_MJ_CLOSE IRP-based operations. To determine whether the operation is an IRP-based operation, use the <a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro.

If the IRP-based operation is an IRP_MJ_CLOSE request, STATUS_INVALID_PARAMETER is returned.

<b>FltRequestOperationStatusCallback</b> copies the contents of the I/O parameter block (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a>) to the <b>Iopb</b> member of the callback data (FLT_CALLBACK_DATA), and this is the callback data that the Filter Manager will pass to the routine specified in the <i>CallbackRoutine</i> parameter. The copied data represents a snapshot of the I/O parameter block at the time that the preoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>) routine calls <b>FltRequestOperationStatusCallback</b>. If the preoperation callback routine changes the I/O parameter block after calling <b>FltRequestOperationStatusCallback</b>, the I/O parameter block that the Filter Manager passes to <i>CallbackRoutine</i> will be different from the I/O parameter block that the filter driver passes down the driver stack when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocalldriver">IoCallDriver</a>.

The following example code from a preoperation callback routine illustrates how this might happen:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PFLT_CALLBACK_DATA Data;
PFLT_GET_OPERATION_STATUS_CALLBACK CallbackRoutine;
PVOID RequesterContext;
...
if (iopb->MajorFunction == IRP_MJ_READ) {
    FltRequestOperationStatusCallback (Data, CallbackRoutine, RequesterContext);
 Data->Iopb->Parameters.Read.ReadBuffer = newBuffer;
    ...
}</pre>
</td>
</tr>
</table></span></div>
In the example, the read buffer is changed after the call to <b>FltRequestOperationStatusCallback</b>, so when the Filter Manager calls <i>CallbackRoutine</i>, it will pass in a pointer to the old buffer instead of the new one. 

The Filter Manager calls the given <i>CallbackRoutine</i> in the context of the originating thread at IRQL <= APC_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_get_operation_status_callback">PFLT_GET_OPERATION_STATUS_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

