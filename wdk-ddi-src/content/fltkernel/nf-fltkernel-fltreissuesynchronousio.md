---
UID: NF:fltkernel.FltReissueSynchronousIo
title: FltReissueSynchronousIo function (fltkernel.h)
description: FltReissueSynchronousIo initiates a new synchronous I/O operation that uses the parameters from a previously synchronized I/O operation.
old-location: ifsk\fltreissuesynchronousio.htm
tech.root: ifsk
ms.assetid: 5feba526-17f3-4969-9199-93cb2a36e937
ms.date: 04/16/2018
keywords: ["FltReissueSynchronousIo function"]
ms.keywords: FltApiRef_p_to_z_c86041cf-780e-4754-b580-6665573bdb88.xml, FltReissueSynchronousIo, FltReissueSynchronousIo function [Installable File System Drivers], fltkernel/FltReissueSynchronousIo, ifsk.fltreissuesynchronousio
f1_keywords:
 - "fltkernel/FltReissueSynchronousIo"
 - "FltReissueSynchronousIo"
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltReissueSynchronousIo
targetos: Windows
req.typenames: 
---

# FltReissueSynchronousIo function


## -description


<b>FltReissueSynchronousIo</b> initiates a new synchronous I/O operation that uses the parameters from a previously synchronized I/O operation. 


## -parameters




### -param InitiatingInstance 
[in]
An opaque instance pointer to the minifilter driver instance that is reissuing the I/O operation. Must be the same instance that initiated the previous I/O operation. This parameter is required and cannot be set to <b>NULL</b>. 


### -param CallbackData 
[in]
A pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure from a previously synchronized I/O operation. This parameter is required and cannot be set to <b>NULL</b>. 


## -returns



None 




## -remarks



A minifilter driver calls <b>FltReissueSynchronousIo</b> from a postoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>) routine to reissue a synchronized I/O request. It typically calls <b>FltReissueSynchronousIo</b> from a postoperation callback routine to reissue a failed operation with different parameters, or to handle a reparse bounce. However, it can also call <b>FltReissueSynchronousIo</b> to reissue I/O that the minifilter driver generated through calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a> routines. In this situation, it does not matter whether it calls <b>FltReissueSynchronousIo</b> in a postoperation callback routine or outside the context of an operation callback routine. For calls outside the context of a postoperation callback routine, consider using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreusecallbackdata">FltReuseCallbackData</a> and <i>FltPerformSynchronousIo</i> routines instead.

The caller can modify the contents of the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure's I/O parameter block before reissuing the I/O request. If it does, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a> before calling <b>FltReissueSynchronousIo</b>. 

For example, if a minifilter driver uses reparse points, and its post-create callback routine is called for a create operation that returned STATUS_REPARSE, the minifilter driver can reissue the create operation for its own reparse points. In this case, the minifilter driver will complete the following steps: 

<ol>
<li>
Set the FILE_OPEN_REPARSE_POINT flag in the callback data structure's I/O parameter block. 

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>. 

</li>
<li>
Call <b>FltReissueSynchronousIo</b> to reissue the create request. 

</li>
</ol>
The Filter Manager sends the reissued I/O request only to the minifilter driver instances that are attached below the initiating instance (specified in the <i>InitiatingInstance</i> parameter) and to the file system. Minifilter driver instances attached above the initiating instance do not receive the reissued I/O request. 

Only synchronized I/O operations can be reissued. To provide the driver with the ability to reissue, by calling <b>FltReissueSynchronousIo</b> in the postoperation callback routine, a minifilter driver must specifically return FLT_PREOP_SYNCHRONIZE in the preoperation callback routine. 

<div class="alert"><b>Note</b>    The minifilter driver does not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisoperationsynchronous">FltIsOperationSynchronous</a> routine to determine whether the preoperation callback routine for this operation returned FLT_PREOP_SYNCHRONIZE. The minifilter driver calls <b>FltIsOperationSynchronous</b> to determine whether the operation itself is synchronous from the I/O manager's perspective. </div>
<div> </div>
Only IRP-based I/O operations can be reissued. Fast I/O operations and file system filter (FSFilter) callback operations cannot be reissued. To determine whether an I/O operation is IRP-based, use the <a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro. 

A create (IRP_MJ_CREATE) operation that has been canceled cannot be reissued. Before calling <b>FltReissueSynchronousIo</b> for a create operation, callers should check the <b>Flags</b> member of the file object for the create operation. If the FO_FILE_OPEN_CANCELLED flag is set, this means that the create operation has been canceled, and a close (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>) operation will be issued for this file object. If <b>FltReissueSynchronousIo</b> is called for a create operation that has been canceled, the Filter Manager fails the reissued I/O request with STATUS_CANCELLED. 

<div class="alert"><b>Note</b>    When minifilter drivers re-issue the create in the post-create callback, they do not have to release and set the buffer that is associated with their reparse point (<b>TagData</b> field in <i>CallbackData</i>) to <b>NULL</b>. Instead, the Filter Manager releases and sets the buffer to <b>NULL</b> for them. </div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">FLT_IS_FASTIO_OPERATION</a>



<a href="https://docs.microsoft.com/previous-versions/ff544648(v=vs.85)">FLT_IS_FS_FILTER_OPERATION</a>



<a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="https://docs.microsoft.com/previous-versions/ff544660(v=vs.85)">FLT_IS_REISSUED_IO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create">FLT_PARAMETERS for IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelfileopen">FltCancelFileOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisoperationsynchronous">FltIsOperationSynchronous</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreusecallbackdata">FltReuseCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

