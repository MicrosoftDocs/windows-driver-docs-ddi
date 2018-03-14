---
UID: NF:fltkernel.FltCancelFileOpen
title: FltCancelFileOpen function
author: windows-driver-content
description: A minifilter driver can use the FltCancelFileOpen routine to close a newly opened or created file.
old-location: ifsk\fltcancelfileopen.htm
old-project: ifsk
ms.assetid: adc1a1fd-ddbc-4ed5-85e3-4d4e85d710b1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_6000a551-04a6-47d6-b2d8-816decb93d89.xml, FltCancelFileOpen, FltCancelFileOpen routine [Installable File System Drivers], fltkernel/FltCancelFileOpen, ifsk.fltcancelfileopen
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltCancelFileOpen
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCancelFileOpen function


## -description


A minifilter driver can use the <b>FltCancelFileOpen</b> routine to close a newly opened or created file. 


## -syntax


````
VOID FltCancelFileOpen(
  _In_ PFLT_INSTANCE Instance,
  _In_ PFILE_OBJECT  FileObject
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



If a minifilter driver determines that a file-open or file-create (<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>) operation must fail after the file system has already completed the operation with a success NTSTATUS value such as STATUS_SUCCESS, the minifilter driver can call <b>FltCancelFileOpen</b> from its post-create callback routine to close the file. 

<div class="alert"><b>Note</b>    Although STATUS_REPARSE is a success NTSTATUS value, it is not necessary to call <b>FltCancelFileOpen</b> for a create operation that was completed with STATUS_REPARSE, because this status value indicates that the file was not successfully opened. </div>
<div> </div>
A successful call to <b>FltCancelFileOpen</b> has the following effect: To minifilter drivers and legacy filters that are above the caller in the minifilter driver instance stack, the create request appears to have failed. To those that are below the caller, the file appears to have been opened (or created) and then closed. 

Note that <b>FltCancelFileOpen</b> does not undo any modifications to the file. For example, <b>FltCancelFileOpen</b> does not delete a newly created file or restore a file that was overwritten or superseded to its previous state. 

<b>FltCancelFileOpen</b> must be called before any handles are created for the file. Callers can check the <b>Flags</b> member of the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure that the <i>FileObject</i> parameter points to. If the FO_HANDLE_CREATED flag is set, this means that one or more handles have been created for the file, so it is not safe to call <b>FltCancelFileOpen</b>. 

<b>FltCancelFileOpen</b> sets the FO_FILE_OPEN_CANCELLED flag in the <b>Flags</b> member of the file object that <i>FileObject</i> points to. This flag indicates that the create operation has been canceled, and a close (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>) request will be issued for this file object. 

Once the create operation has been canceled, it cannot be reissued. For more information, see <a href="..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md">FltReissueSynchronousIo</a>. 

<b>FltCancelFileOpen</b> can only be called from a minifilter driver's post-create callback routine. Calling <b>FltCancelFileOpen</b> from a postoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routine for any other type of I/O operation, or calling it from a preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine, is a programming error. 

Callers of <b>FltCancelFileOpen</b> must be running at IRQL PASSIVE_LEVEL. However, it is safe for minifilter drivers to call this routine from a post-create callback routine, because post-create callback routines are guaranteed to be called at IRQL PASSIVE_LEVEL, in the context of the thread that originated the IRP_MJ_CREATE request. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544687">FLT_PARAMETERS for IRP_MJ_CREATE</a>



<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md">FltReissueSynchronousIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544660">FLT_IS_REISSUED_IO</a>



<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>



<a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>



<a href="..\ntddk\nf-ntddk-iocancelfileopen.md">IoCancelFileOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCancelFileOpen routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

