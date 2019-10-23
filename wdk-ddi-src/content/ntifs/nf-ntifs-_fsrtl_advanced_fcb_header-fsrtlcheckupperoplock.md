---
UID: NF:ntifs.FsRtlCheckUpperOplock
title: FsRtlCheckUpperOplock function (ntifs.h)
description: The FsRtlCheckUpperOplock routine provides opportunistic lock (oplock) checking in secondary, or layered, file systems when the oplocks they hold change state.
old-location: ifsk\fsrtlcheckupperoplock.htm
tech.root: ifsk
ms.assetid: 36439793-DEE4-48A8-87C4-25BB11BA9CE5
ms.date: 04/16/2018
ms.keywords: FsRtlCheckUpperOplock, FsRtlCheckUpperOplock routine [Installable File System Drivers], OPLOCK_LEVEL_CACHE_HANDLE, OPLOCK_LEVEL_CACHE_READ, OPLOCK_LEVEL_CACHE_WRITE, ifsk.fsrtlcheckupperoplock, ntifs/FsRtlCheckUpperOplock
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlCheckUpperOplock"
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
- FsRtlCheckUpperOplock
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlCheckUpperOplock function


## -description


The <b>FsRtlCheckUpperOplock</b> routine provides opportunistic lock (oplock) checking  in secondary, or layered, file systems when the oplocks they hold change state. Secondary file systems, such as network redirectors and clustering file services, call <b>FsRtlCheckUpperOplock</b> when an oplock held in a lower file system by the secondary file system, changes state. A state change can occur either by a break or an upgrade. <b>FsRtlCheckUpperOplock</b> will break the oplock of upper file system, if necessary, to confirm the new lower oplock state. The caller can also provide optional callbacks for notifications of break acknowledgment and pending status.


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 


### -param NewLowerOplockState [in]

A value representing the requested oplock held in a lower file system by a secondary file system. This a bitwise OR combination of the following:

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
 


### -param CompletionRoutineContext [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that the <i>CompletionRoutine</i> and <i>PrePendIrpRoutine</i> parameters point to. 


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
      _In_ PVOID Context,
      _In_opt_ PIRP Irp
      );</pre>
</td>
</tr>
</table></span></div>
This routine has the following parameters: 





#### Context

A context information pointer that was passed in the <i>CompletionRoutineContext</i> parameter to <b>FsRtlCheckUpperOplock</b>. 



#### Irp

A optional pointer to the IRP for the I/O operation <b>FsRtlCheckUpperOplock</b> will always set this to NULL. 


### -param PrePendRoutine

<p>A pointer to a caller-supplied callback routine to be called if <b>FsRtlCheckUpperOplock</b> will return STATUS_PENDING. This parameter is optional and can be <b>NULL</b>. </p>
  <p>This routine is declared as follows: </p>
  <div class="code">
    <span codelanguage="">
      <table>
        <tr>
          <th></th>
        </tr>
        <tr>
          <td>
            <pre>typedef VOID
(*POPLOCK_FS_PREPOST_IRP) (
      _In_ PVOID Context,
      _in_opt_ PIRP Irp
      );</pre>
          </td>
        </tr>
      </table>
    </span>
  </div>
  <p></p>
  <dl>
    <dt>
      <a id="Context"></a>
      <a id="context"></a>
      <a id="CONTEXT"></a>
      <i>Context</i>
    </dt>
    
      <p>A context information pointer that was passed in the <i>CompletionRoutineContext</i> parameter to <b>FsRtlCheckUpperOplock</b>. </p>
    
    <dt>
      <a id="Irp"></a>
      <a id="irp"></a>
      <a id="IRP"></a>
      <i>Irp</i>
    </dt>
    
      <p>A optional pointer to the IRP for the I/O operation. <b>FsRtlCheckUpperOplock</b> will always set this to NULL.</p>
    
  </dl>


### -param Flags [in]

A bitmask for the associated file I/O operation. A file system or filter driver sets bits to specify the behavior of <b>FsRtlCheckUpperOplock</b>. The <i>Flags</i> parameter has the following options:





#### OPLOCK_UPPER_FLAG_CHECK_NO_BREAK   (0x00010000)

Return STATUS_CANNOT_BREAK_OPLOCK if the value of <i>NewLowerOplockState</i> results in any oplock break.



#### OPLOCK_UPPER_FLAG_NOTIFY_REFRESH_READ   (0x00020000)

Break only Read (R) upper oplocks and notify R holders that they may again request R.  All other upper oplock checks it will return STATUS_CANNOT_BREAK_OPLOCK.


## -returns



<b>FsRtlCheckUpperOplock</b> returns an appropriate NTSTATUS code such as one of the following: 

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
An oplock break is not required or the break was acknowledged. If <i>CompletionRoutine</i> is <b>NULL</b>, <b>FsRtlCheckUpperOplock</b> blocks while the oplock break is processed rather than return STATUS_PENDING.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANNOT_BREAK_OPLOCK</b></dt>
</dl>
</td>
<td width="60%">
The oplock break cannot be accomplished. See <i>Flags</i> for conditions that restrict a break.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
An opportunistic lock break is underway. If supplied, <i>PrePendIrpRoutine</i> is called as a notification of the pending operation.  <i>CompletionRoutine</i> is called when the oplock break is complete. STATUS_PENDING is a success code. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckoplockex">FsRtlCheckOplockEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlupperoplockfsctrl">FsRtlUpperOplockFsctrl</a>
 

 

