---
UID: NF:ntifs.FsRtlUpperOplockFsctrl
title: FsRtlUpperOplockFsctrl function (ntifs.h)
description: The FsRtlUpperOplockFsctrl routine processes opportunistic lock (oplock) requests and acknowledgments for secondary, or layered, file systems.
old-location: ifsk\fsrtlupperoplockfsctrl.htm
tech.root: ifsk
ms.assetid: 1E3C48A0-A161-481C-BF69-69D3FA7B941F
ms.date: 04/16/2018
keywords: ["FsRtlUpperOplockFsctrl function"]
ms.keywords: FsRtlUpperOplockFsctrl, FsRtlUpperOplockFsctrl routine [Installable File System Drivers], OPLOCK_LEVEL_CACHE_HANDLE, OPLOCK_LEVEL_CACHE_READ, OPLOCK_LEVEL_CACHE_WRITE, ifsk.fsrtlupperoplockfsctrl, ntifs/FsRtlUpperOplockFsctrl
f1_keywords:
 - "ntifs/FsRtlUpperOplockFsctrl"
 - "FsRtlUpperOplockFsctrl"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: IRQL <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlUpperOplockFsctrl
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlUpperOplockFsctrl function


## -description


The <b>FsRtlUpperOplockFsctrl</b> routine processes opportunistic lock (oplock) requests and acknowledgments for secondary, or layered, file systems. The upper file system submits the state of the oplock held in the lower file system. <b>FsRtlUpperOplockFsctrl</b> will determine whether to grant or deny the upper file system oplock.


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>.


### -param Irp [in]

A pointer to the IRP for the I/O operation.


### -param OpenCount [in]

Number of user handles for the file, if an exclusive oplock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For information about oplock types, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/overview">Oplock Semantics Overview</a>.


### -param LowerOplockState [in]

The value the lower oplock level held by the upper file system. This a bitwise OR combination of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="OPLOCK_LEVEL_CACHE_READ"></a><a id="oplock_level_cache_read"></a><dl>
<dt><b>OPLOCK_LEVEL_CACHE_READ</b></dt>
</dl>
</td>
<td width="60%">
Indicates an oplock Read (R) type.

</td>
</tr>
<tr>
<td width="40%"><a id="OPLOCK_LEVEL_CACHE_WRITE"></a><a id="oplock_level_cache_write"></a><dl>
<dt><b>OPLOCK_LEVEL_CACHE_WRITE</b></dt>
</dl>
</td>
<td width="60%">
Indicates an oplock Write (W) type.

</td>
</tr>
<tr>
<td width="40%"><a id="OPLOCK_LEVEL_CACHE_HANDLE"></a><a id="oplock_level_cache_handle"></a><dl>
<dt><b>OPLOCK_LEVEL_CACHE_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates an oplock Handle (H) type.

</td>
</tr>
</table>
 


### -param Flags [in]

A bitmask for the associated oplock operations. A file system or filter driver sets bits to specify the behavior of <b>FsRtlUpperOplockFsctrl</b>. The <i>Flags</i> parameter has the following options:





#### OPLOCK_FSCTRL_FLAG_ALL_KEYS_MATCH (0x00000001)

Specifies that the file system verified that all oplock keys on any currently open handles match. By specifying this flag, you allow the oplock package to grant an oplock of level RW or RWH when more than one open handle to the file exists. For more information about oplock types, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/overview">Oplock Semantics Overview</a> page. 


## -returns



<b>FsRtlUpperOplockFsctrl</b> returns one of the following NTSTATUS values: 

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
For an IRP_MJ_CREATE request, STATUS_SUCCESS indicates that the requested filter opportunistic lock (oplock) was granted. For a FSCTL operation, the meaning of STATUS_SUCCESS depends on the FSCTL code. For more information, see the Remarks section in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrlex">FsRtlOplockFsctrlEx</a>. 

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
The FSCTL code for the I/O operation was not a valid values oplock request. Valid request types are  listed in the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrlex">FsRtlOplockFsctrlEx</a>. STATUS_INVALID_PARAMETER is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OPLOCK_NOT_GRANTED</b></dt>
</dl>
</td>
<td width="60%">
The oplock could not be granted. The level of the requested upper file system oplock is not valid for the oplock granted for the lower file system. STATUS_OPLOCK_NOT_GRANTED is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Used only for FSCTL operations. The meaning of STATUS_PENDING depends on the FSCTL code. For more information, see the Remarks section in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrlex">FsRtlOplockFsctrlEx</a>. STATUS_PENDING is a success code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANNOT_GRANT_REQUESTED_OPLOCK</b></dt>
</dl>
</td>
<td width="60%">
An oplock acknowledgement
                                           for a new oplock is not allowed. The level of the upper file system of lock is not valid for the lower file system oplock.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckupperoplock">FsRtlCheckUpperOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrlex">FsRtlOplockFsctrlEx</a>
 

 

