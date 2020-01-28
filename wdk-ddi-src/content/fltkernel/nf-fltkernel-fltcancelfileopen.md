---
UID: NF:fltkernel.FltCancelFileOpen
title: FltCancelFileOpen function (fltkernel.h)
description: A minifilter driver can use the FltCancelFileOpen routine to close a newly opened or created file.
old-location: ifsk\fltcancelfileopen.htm
tech.root: ifsk
ms.assetid: adc1a1fd-ddbc-4ed5-85e3-4d4e85d710b1
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_6000a551-04a6-47d6-b2d8-816decb93d89.xml, FltCancelFileOpen, FltCancelFileOpen routine [Installable File System Drivers], fltkernel/FltCancelFileOpen, ifsk.fltcancelfileopen
f1_keywords:
 - "fltkernel/FltCancelFileOpen"
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltCancelFileOpen
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCancelFileOpen function


## -description


A minifilter driver can use the <b>FltCancelFileOpen</b> routine to close a newly opened or created file. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



If a minifilter driver determines that a file-open or file-create (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>) operation must fail after the file system has already completed the operation with a success NTSTATUS value such as STATUS_SUCCESS, the minifilter driver can call <b>FltCancelFileOpen</b> from its post-create callback routine to close the file. 

<div class="alert"><b>Note</b>    Although STATUS_REPARSE is a success NTSTATUS value, it is not necessary to call <b>FltCancelFileOpen</b> for a create operation that was completed with STATUS_REPARSE, because this status value indicates that the file was not successfully opened. </div>
<div> </div>
A successful call to <b>FltCancelFileOpen</b> has the following effect: To minifilter drivers and legacy filters that are above the caller in the minifilter driver instance stack, the create request appears to have failed. To those that are below the caller, the file appears to have been opened (or created) and then closed. 

Note that <b>FltCancelFileOpen</b> does not undo any modifications to the file. For example, <b>FltCancelFileOpen</b> does not delete a newly created file or restore a file that was overwritten or superseded to its previous state. 

<b>FltCancelFileOpen</b> must be called before any handles are created for the file. Callers can check the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure that the <i>FileObject</i> parameter points to. If the FO_HANDLE_CREATED flag is set, this means that one or more handles have been created for the file, so it is not safe to call <b>FltCancelFileOpen</b>. 

<b>FltCancelFileOpen</b> sets the FO_FILE_OPEN_CANCELLED flag in the <b>Flags</b> member of the file object that <i>FileObject</i> points to. This flag indicates that the create operation has been canceled, and a close (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>) request will be issued for this file object. 

Once the create operation has been canceled, it cannot be reissued. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreissuesynchronousio">FltReissueSynchronousIo</a>. 

<b>FltCancelFileOpen</b> can only be called from a minifilter driver's post-create callback routine. Calling <b>FltCancelFileOpen</b> from a postoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>) routine for any other type of I/O operation, or calling it from a preoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>) routine, is a programming error. 

Callers of <b>FltCancelFileOpen</b> must be running at IRQL PASSIVE_LEVEL. However, it is safe for minifilter drivers to call this routine from a post-create callback routine, because post-create callback routines are guaranteed to be called at IRQL PASSIVE_LEVEL, in the context of the thread that originated the IRP_MJ_CREATE request. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/previous-versions/ff544660(v=vs.85)">FLT_IS_REISSUED_IO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create">FLT_PARAMETERS for IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreissuesynchronousio">FltReissueSynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocancelfileopen">IoCancelFileOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

