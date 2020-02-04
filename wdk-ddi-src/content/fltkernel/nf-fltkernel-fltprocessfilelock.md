---
UID: NF:fltkernel.FltProcessFileLock
title: FltProcessFileLock function (fltkernel.h)
description: The FltProcessFileLock routine processes and completes a file lock operation.
old-location: ifsk\fltprocessfilelock.htm
tech.root: ifsk
ms.assetid: 72b8aad8-39e1-4624-ac77-13eb52036b3b
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_e4ff8145-c586-4c3c-acfa-d4c22f48a5d2.xml, FltProcessFileLock, FltProcessFileLock routine [Installable File System Drivers], fltkernel/FltProcessFileLock, ifsk.fltprocessfilelock
f1_keywords:
 - "fltkernel/FltProcessFileLock"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows XP with SP2 or Windows Server 2003 with SP1.
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
- FltProcessFileLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltProcessFileLock function


## -description


The <b>FltProcessFileLock</b> routine processes and completes a file lock operation.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializefilelock">FltInitializeFileLock</a>. 


### -param CallbackData [in]

Pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-lock-control">IRP_MJ_LOCK_CONTROL</a> operation. 


### -param Context [in, optional]

Context pointer to be used when completing the operation. This context pointer is passed to the <i>CompleteLockCallbackDataRoutine</i> and <i>UnlockRoutine</i> callback routines that the minifilter driver registered in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltProcessFileLock</b> returns one of the following. 

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
The Filter Manager is done with the <i>CallbackData</i>, which can now be completed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_DISALLOW_FASTIO</b></dt>
</dl>
</td>
<td width="60%">
The <i>CallbackData</i> represents a fast I/O operation, and a minifilter driver in the stack has disallowed the fast I/O to be used for this operation. The Filter Manager does not send the operation to any minifilter drivers below the one that disallowed the operation. In this case, the Filter Manager only calls the postoperation callback routines (and <i>CompleteLockCallbackDataRoutine</i> callbacks) of the minifilter drivers above the minifilter driver that disallowed the fast I/O operation. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The lock operation has been pended. 

</td>
</tr>
</table>
 




## -remarks



<b>FltProcessFileLock</b> processes a file lock (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-lock-control">IRP_MJ_LOCK_CONTROL</a>) operation. The lock operation can be a fast I/O or IRP-based operation. 

For unlock operations, the Filter Manager calls the <i>UnlockRoutine</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/punlock-routine">PUNLOCK_ROUTINE</a>) callback routine that the caller registered for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>. 

When the lock operation is completed, the Filter Manager calls the <i>CompleteLockCallbackDataRoutine</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_complete_lock_callback_data_routine">PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</a>) completion callback routine that the caller registered for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>. 

When the <i>CallbackData</i> parameter passed to <b>FltProcessFileLock</b> represents a fast I/O operation, the callback specified in <i>CompleteLockCallbackDataRoutine</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a> routine is not invoked. Only when the I/O operation in <i>CallbackData</i> is an IRP, and <i>CompleteLockCallbackDataRoutine</i> is not NULL, will the callback routine be called.

To determine whether the <i>CallbackData</i> represents a fast I/O operation, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">FLT_IS_FASTIO_OPERATION</a> macro. 

To allocate and initialize a new file lock structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>. 

To free an initialized<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreefilelock">FltFreeFileLock</a>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">FLT_IS_FASTIO_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltchecklockforreadaccess">FltCheckLockForReadAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltchecklockforwriteaccess">FltCheckLockForWriteAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreefilelock">FltFreeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializefilelock">FltInitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuninitializefilelock">FltUninitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlprocessfilelock">FsRtlProcessFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-lock-control">IRP_MJ_LOCK_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_complete_lock_callback_data_routine">PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/punlock-routine">PUNLOCK_ROUTINE</a>
 

 

