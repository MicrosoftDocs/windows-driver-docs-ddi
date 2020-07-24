---
UID: NF:ntifs.FsRtlCheckOplock
title: FsRtlCheckOplock function (ntifs.h)
description: The FsRtlCheckOplock routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state.
old-location: ifsk\fsrtlcheckoplock.htm
tech.root: ifsk
ms.assetid: e1430ef2-fb94-4f0d-bdc8-59b423fe9c8c
ms.date: 04/16/2018
keywords: ["FsRtlCheckOplock function"]
ms.keywords: FsRtlCheckOplock, FsRtlCheckOplock routine [Installable File System Drivers], fsrtlref_c11dbb80-c7a8-437d-bb6b-661edcf2f24a.xml, ifsk.fsrtlcheckoplock, rxprocs/FsRtlCheckOplock
f1_keywords:
 - "ntifs/FsRtlCheckOplock"
 - "FsRtlCheckOplock"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available in Microsoft Windows 2000 and later versions of Windows operating systems.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlCheckOplock
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlCheckOplock function


## -description


The <b>FsRtlCheckOplock</b> routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state. 


## -parameters




### -param Oplock [in]

An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 


### -param Irp [in]

A pointer to the IRP for the I/O operation. 


### -param Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that the <i>CompletionRoutine</i> and <i>PostIrpRoutine </i>parameters point to. 


### -param CompletionRoutine [in, optional]

A pointer to a caller-supplied callback routine. If an opportunistic lock break is in progress, this routine is called when the break is completed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the caller is put into a wait state until the opportunistic lock break is completed. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*POPLOCK_WAIT_COMPLETE_ROUTINE) (
      IN PVOID Context,
      IN PIRP Irp
      );</pre>
</td>
</tr>
</table></span></div>
This routine has the following parameters: 





#### Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlCheckOplock</b>. 



#### Irp

A pointer to the IRP for the I/O operation. 


### -param PostIrpRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if the I/O operation is posted to a work queue. This parameter is optional and can be <b>NULL</b>. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*POPLOCK_FS_PREPOST_IRP) (
      IN PVOID Context,
      IN PIRP Irp
      );</pre>
</td>
</tr>
</table></span></div>




#### Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlCheckOplock</b>. 



#### Irp

A pointer to the IRP for the I/O operation. 


## -returns



The <b>FsRtlCheckOplock</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The IRP was canceled. STATUS_CANCELLED is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANNOT_BREAK_OPLOCK </b></dt>
</dl>
</td>
<td width="60%">
If the IRP is an IRP_MJ_CREATE and FILE_OPEN_REQUIRING_OPLOCK is in the IRP's CreateOptions, the routine will not initiate a break of an existing opportunistic lock, but fails with STATUS_CANNOT_BREAK_OPLOCK. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OPLOCK_BREAK_IN_PROGRESS</b></dt>
</dl>
</td>
<td width="60%">
An opportunistic lock break is underway. The IRP is an IRP_MJ_CREATE request, and FILE_COMPLETE_IF_OPLOCKED was specified in the create options parameter for the operation. STATUS_OPLOCK_BREAK_IN_PROGRESS is a success code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
An opportunistic lock break has been initiated, and control of the IRP has been passed to the oplock package. If CompletionRoutine is <b>NULL</b>, this routine will block while the oplock break is processed, rather than return STATUS_PENDING. STATUS_PENDING is a success code. 

</td>
</tr>
</table>
 




## -remarks



<b>FsRtlCheckOplock</b> synchronizes the IRP for an I/O operation with the current opportunistic lock state of a file according to the following conditions: 

<ul>
<li>
If the I/O operation will cause the opportunistic lock to break, the opportunistic lock break is initiated. 

</li>
<li>
If the I/O operation cannot continue until the opportunistic lock break is complete, <b>FsRtlCheckOplock</b> returns STATUS_PENDING and calls the callback routine that the <i>PostIrpRoutine</i> parameter points to. 

</li>
</ul>
If a file system or filter driver uses opportunistic locks, it must call <b>FsRtlCheckOplock</b> from any dispatch routines for I/O operations that can cause opportunistic lock breaks. This rule applies to the following types of I/O operations, because these operations can cause opportunistic lock breaks: 

IRP_MJ_CLEANUP

IRP_MJ_CREATE

IRP_MJ_FILE_SYSTEM_CONTROL

IRP_MJ_FLUSH_BUFFERS

IRP_MJ_LOCK_CONTROL

IRP_MJ_READ

IRP_MJ_SET_INFORMATION

IRP_MJ_WRITE

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcheckoplock">FltCheckOplock</a> instead of <b>FsRtlCheckOplock</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcheckoplock">FltCheckOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock">FsRtlCurrentBatchOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl">FsRtlOplockFsctrl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockisfastiopossible">FsRtlOplockIsFastIoPossible</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock">FsRtlUninitializeOplock</a>
 

 

