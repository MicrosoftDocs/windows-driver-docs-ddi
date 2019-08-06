---
UID: NF:ntifs.FsRtlOplockFsctrl
title: FsRtlOplockFsctrl function (ntifs.h)
description: FsRtlOplockFsctrl performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver.
old-location: ifsk\fsrtloplockfsctrl.htm
tech.root: ifsk
ms.assetid: e456189e-9513-47a7-b5b0-384b531dbda9
ms.date: 04/16/2018
ms.keywords: FsRtlOplockFsctrl, FsRtlOplockFsctrl function [Installable File System Drivers], fsrtlref_74e6bade-f196-4117-9e94-c33776c4f9cd.xml, ifsk.fsrtloplockfsctrl, ntifs/FsRtlOplockFsctrl
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlOplockFsctrl"
req.header: ntifs.h
req.include-header: Ntifs.h
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
- FsRtlOplockFsctrl
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlOplockFsctrl function


## -description


<b>FsRtlOplockFsctrl</b> performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver. 


## -parameters




### -param Oplock [in]

Opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 


### -param Irp [in]

Pointer to the IRP for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


### -param OpenCount [in]

Number of user handles for the file, if an exclusive opportunistic lock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For information about oplock types, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/overview">Oplock Semantics Overview</a>. 


## -returns



<b>FsRtlOplockFsctrl</b> returns one of the following NTSTATUS values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
For an IRP_MJ_CREATE request, STATUS_SUCCESS indicates that the requested filter opportunistic lock was granted. For a FSCTL operation, the meaning of STATUS_SUCCESS depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes listed in the following Remarks section. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The I/O operation was canceled. STATUS_CANCELLED is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The FSCTL code for the I/O operation was not one of the valid values listed in the following Remarks section. STATUS_INVALID_PARAMETER is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OPLOCK_NOT_GRANTED</b></dt>
</dl>
</td>
<td width="60%">
The opportunistic lock could not be granted. STATUS_OPLOCK_NOT_GRANTED is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Used only for FSCTL operations. The meaning of STATUS_PENDING depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes listed in the following Remarks section. STATUS_PENDING is a success code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANNOT_BREAK_OPLOCK </b></dt>
</dl>
</td>
<td width="60%">
A new opportunistic lock (oplock) could not be granted. The IRP is an IRP_MJ_CREATE request and FILE_OPEN_REQUIRING_OPLOCK was specified in the create options parameter for the operation. STATUS_CANNOT_BREAK_OPLOCK is a success code. 

</td>
</tr>
</table>
 




## -remarks



File systems and filter drivers call <b>FsRtlOplockFsctrl</b> to perform various opportunistic lock operations for a create or file system control I/O operation. The IRP pointed to by the <i>Irp</i> parameter must be a valid IRP for an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-file-system-control">IRP_MJ_FILE_SYSTEM_CONTROL</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> operation. 

If the IRP is an IRP_MJ_FILE_SYSTEM_CONTROL request, <b>FsRtlOplockFsctrl</b> can be used with the following FSCTL codes. The FSCTL code is set in IrpSp->Parameters.FileSystemControl.FsControlCode. For more information about file system control parameters, see the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-file-system-control">IRP_MJ_FILE_SYSTEM_CONTROL</a>. 


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>


For detailed information about these FSCTLs and about opportunistic locks in general, see the Microsoft Windows SDK documentation. 

If the IRP is an IRP_MJ_CREATE request, <b>FsRtlOplockFsctrl</b> can be used to request a pending filter opportunistic lock if all of the following conditions are true: 

<ul>
<li>
The value of the <i>OpenCount</i> parameter must be 1. 

</li>
<li>
The value of the <i>DesiredAccess</i> parameter for the IRP_MJ_CREATE request must be FILE_READ_ATTRIBUTES. 

</li>
<li>
The value of the <i>ShareAccess</i> parameter for the IRP_MJ_CREATE request must be FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE. 

</li>
</ul>
If the request for a pending filter opportunistic lock is granted, <b>FsRtlOplockFsctrl</b> returns STATUS_SUCCESS. For more information about create parameters, see the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>. 

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltoplockfsctrl">FltOplockFsctrl</a> instead of <b>FsRtlOplockFsctrl</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltoplockfsctrl">FltOplockFsctrl</a>



<a href="https://docs.microsoft.com/windows/desktop/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize">FsRtlCheckOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock">FsRtlCurrentBatchOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockisfastiopossible">FsRtlOplockIsFastIoPossible</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock">FsRtlUninitializeOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-file-system-control">IRP_MJ_FILE_SYSTEM_CONTROL</a>
 

 

