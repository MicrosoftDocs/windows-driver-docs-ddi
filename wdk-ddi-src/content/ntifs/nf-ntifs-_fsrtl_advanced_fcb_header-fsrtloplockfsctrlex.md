---
UID: NF:ntifs.FsRtlOplockFsctrlEx
title: FsRtlOplockFsctrlEx function (ntifs.h)
description: The FsRtlOplockFsctrlEx routine performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver.
old-location: ifsk\fsrtloplockfsctrlex.htm
tech.root: ifsk
ms.assetid: f1bac8c1-a313-40b9-96fc-9eaf426bf238
ms.date: 04/16/2018
keywords: ["FsRtlOplockFsctrlEx function"]
ms.keywords: FsRtlOplockFsctrlEx, FsRtlOplockFsctrlEx routine [Installable File System Drivers], fsrtlref_fa242815-36f3-4c0a-ae1d-826d0208e191.xml, ifsk.fsrtloplockfsctrlex, ntifs/FsRtlOplockFsctrlEx
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlOplockFsctrlEx routine is available starting with Windows 7.
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlOplockFsctrlEx
 - ntifs/FsRtlOplockFsctrlEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlOplockFsctrlEx
dev_langs:
 - c++
---

# FsRtlOplockFsctrlEx function


## -description

The <b>FsRtlOplockFsctrlEx</b> routine performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver.

## -parameters

### -param Oplock 

[in]
An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>.

### -param Irp 

[in]
A pointer to the IRP for the I/O operation. This parameter is required and cannot be <b>NULL</b>.

### -param OpenCount 

[in]
Number of user handles for the file, if an exclusive oplock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For information about oplock types, see <a href="/windows-hardware/drivers/image/overview">Oplock Semantics Overview</a>.

### -param Flags 

[in]
A bitmask for the associated oplock operations. A file system or filter driver sets bits to specify the behavior of <b>FsRtlOplockFsctrlEx</b>. The <i>Flags</i> parameter has the following options:





#### OPLOCK_FSCTRL_FLAG_ALL_KEYS_MATCH (0x00000001)

Specifies that the file system verified that all oplock keys on any currently open handles match. By specifying this flag, you allow the oplock package to grant an oplock of level RW or RWH when more than one open handle to the file exists. For more information about oplock types, see the Oplock Semantics <a href="/windows-hardware/drivers/image/overview">Overview</a> page.

## -returns

<b>FsRtlOplockFsctrlEx</b> returns one of the following NTSTATUS values: 

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
For an IRP_MJ_CREATE request, STATUS_SUCCESS indicates that the requested filter opportunistic lock (oplock) was granted. For a FSCTL operation, the meaning of STATUS_SUCCESS depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes that are listed in the following Remarks section. 

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
The oplock could not be granted. STATUS_OPLOCK_NOT_GRANTED is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Used only for FSCTL operations. The meaning of STATUS_PENDING depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes that are listed in the following Remarks section. STATUS_PENDING is a success code. 

</td>
</tr>
</table>

## -remarks

File systems and filter drivers call <b>FsRtlOplockFsctrlEx</b> to perform various opportunistic lock operations for a create operation or file system control I/O operation. The IRP pointed to by the <i>Irp</i> parameter must be a valid IRP for an <a href="/windows-hardware/drivers/kernel/irp-mj-file-system-control">IRP_MJ_FILE_SYSTEM_CONTROL</a> or <a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> operation. 

If the IRP is an IRP_MJ_FILE_SYSTEM_CONTROL request, <b>FsRtlOplockFsctrlEx</b> can be used with the following FSCTL codes. The FSCTL code is set in IrpSp->Parameters.FileSystemControl.FsControlCode. For more information about file system control parameters, see the reference entry for <a href="/windows-hardware/drivers/kernel/irp-mj-file-system-control">IRP_MJ_FILE_SYSTEM_CONTROL</a>. 


<a href="/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock">FSCTL_REQUEST_OPLOCK</a>


For more information about these FSCTLs and about opportunistic locks in general, see the Microsoft Windows SDK documentation. 

If the IRP is an IRP_MJ_CREATE request, <b>FsRtlOplockFsctrlEx</b> can be used to request a pending filter opportunistic lock (oplock) if all of the following conditions are true: 

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
If the request for a pending filter oplock is granted, <b>FsRtlOplockFsctrlEx</b> returns STATUS_SUCCESS. For more information about create parameters, see <a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>. 

Minifilters should call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockfsctrlex">FltOplockFsctrlEx</a> instead of <b>FsRtlOplockFsctrlEx</b>.

## -see-also

<a href="/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock">FSCTL_REQUEST_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockfsctrlex">FltOplockFsctrlEx</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="/windows-hardware/drivers/kernel/irp-mj-file-system-control">IRP_MJ_FILE_SYSTEM_CONTROL</a>