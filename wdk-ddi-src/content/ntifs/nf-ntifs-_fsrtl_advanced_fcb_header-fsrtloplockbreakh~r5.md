---
UID: NF:ntifs.FsRtlOplockBreakH~r5
title: FsRtlOplockBreakH function (ntifs.h)
description: The FsRtlOplockBreakH routine breaks CACHE_HANDLE_LEVEL opportunistic locks (oplocks).
old-location: ifsk\fsrtloplockbreakh.htm
tech.root: ifsk
ms.assetid: c533fb15-ca3a-44b2-8a1b-03b2b9c93fc6
ms.date: 03/29/2018
keywords: ["FsRtlOplockBreakH function"]
ms.keywords: FsRtlOplockBreakH, FsRtlOplockBreakH routine [Installable File System Drivers], fsrtlref_fe992b81-62d1-4f86-9615-05bca958411b.xml, ifsk.fsrtloplockbreakh, ntifs/FsRtlOplockBreakH
f1_keywords:
 - "ntifs/FsRtlOplockBreakH"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlOplockBreakH routine is available starting with Windows 7.
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
- FsRtlOplockBreakH
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlOplockBreakH function


## -description


The <b>FsRtlOplockBreakH</b> routine breaks CACHE_HANDLE_LEVEL opportunistic locks (oplocks).


## -parameters




### -param Oplock [in]

An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>.


### -param Irp [in]

A pointer to the IRP for the I/O operation.


### -param Flags [in]

A bitmask for the associated file I/O operation. A file system or filter driver sets bits to specify the behavior of <b>FsRtlOplockBreakH</b>. The <i>Flags</i> parameter has the following options:





#### OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001)

Specifies to allow an oplock break to proceed without blocking or pending the operation that caused the oplock break.



#### OPLOCK_FLAG_IGNORE_OPLOCK_KEYS (0x00000008)

Supported in Windows 7 and later versions.

Specifies to allow CACHE_HANDLE_LEVEL oplock breaks to proceed regardless of the oplock key.


### -param Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that the <i>CompletionRoutine</i> and <i>PostIrpRoutine </i>parameters point to.


### -param CompletionRoutine [in, optional]

A pointer to a caller-supplied callback routine. If an oplock break is in progress, this routine is called when the break is completed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the caller is put into a wait state until the oplock break is completed.

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

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlOplockBreakH</b>.



#### Irp

A pointer to the IRP for the I/O operation.


### -param PostIrpRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if the I/O operation is to be pended. The routine is called before the oplock package pends the IRP. This parameter is optional and can be <b>NULL</b>.

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

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlOplockBreakH</b>.



#### Irp

A pointer to the IRP for the I/O operation.


## -returns



<b>FsRtlOplockBreakH </b>returns STATUS_SUCCESS or an appropriate NTSTATUS code, such as one of the following:

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
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The IRP was posted to a work queue. STATUS_PENDING is a success code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANNOT_BREAK_OPLOCK</b></dt>
</dl>
</td>
<td width="60%">
The opportunistic lock (oplock) break cannot be accomplished. The IRP is an IRP_MJ_CREATE request. FILE_OPEN_REQUIRING_OPLOCK was specified in the create options parameter for the operation, and there is a granted oplock. STATUS_CANNOT_BREAK_OPLOCK is an error code.

</td>
</tr>
</table>
 




## -remarks



When an operation must break CACHE_HANDLE_LEVEL oplocks, the operation calls <b>FsRtlOplockBreakH</b>.

If the caller specifies the OPLOCK_FLAG_IGNORE_OPLOCK_KEYS flag in the <i>Flags</i> parameter, <b>FsRtlOplockBreakH</b> breaks all CACHE_HANDLE_LEVEL oplocks, regardless of the oplock key. The default behavior of <b>FsRtlOplockBreakH</b> is to break oplocks whose keys do not match the key on the caller's file object.

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockbreakh">FltOplockBreakH</a> instead of <b>FsRtlOplockBreakH</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockbreakh">FltOplockBreakH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>
 

 

