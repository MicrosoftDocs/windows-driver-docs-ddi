---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlCheckUpperOplock~r5
title: FsRtlCheckUpperOplock function
author: windows-driver-content
description: The FsRtlCheckUpperOplock routine provides opportunistic lock (oplock) checking in secondary, or layered, file systems when the oplocks they hold change state.
old-location: ifsk\fsrtlcheckupperoplock.htm
old-project: ifsk
ms.assetid: 36439793-DEE4-48A8-87C4-25BB11BA9CE5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlCheckUpperOplock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlCheckUpperOplock
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# FsRtlCheckUpperOplock function



## -description
The <b>FsRtlCheckUpperOplock</b> routine provides opportunistic lock (oplock) checking  in secondary, or layered, file systems when the oplocks they hold change state. Secondary file systems, such as network redirectors and clustering file services, call <b>FsRtlCheckUpperOplock</b> when an oplock held in a lower file system by the secondary file system, changes state. A state change can occur either by a break or an upgrade. <b>FsRtlCheckUpperOplock</b> will break the oplock of upper file system, if necessary, to confirm the new lower oplock state. The caller can also provide optional callbacks for notifications of break acknowledgment and pending status.



## -syntax

````
NTSTATUS FsRtlCheckUpperOplock(
  _In_     POPLOCK                       Oplock,
  _In_     ULONG                         NewLowerOplockState,
  _In_opt_ PVOID                         CompletionRoutineContext,
  _In_opt_ POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine,
  _In_opt_ POPLOCK_FS_PREPOST_IRP        PrePendIrpRoutine,
  _In_     ULONG                         Flags
);
````


## -parameters

### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 


### -param NewLowerOplockState [in]

A value representing the requested oplock held in a lower file system by a secondary file system. This a bitwise OR combination of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param OPLOCK_LEVEL_CACHE_READ

</td>
<td width="60%">
Indicates an oplock Read (R) type.

</td>
</tr>
<tr>

### -param OPLOCK_LEVEL_CACHE_WRITE

</td>
<td width="60%">
Indicates an oplock Write (W) type.

</td>
</tr>
<tr>

### -param OPLOCK_LEVEL_CACHE_HANDLE

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




### -param Context

A context information pointer that was passed in the <i>CompletionRoutineContext</i> parameter to <b>FsRtlCheckUpperOplock</b>. 


### -param Irp

A optional pointer to the IRP for the I/O operation <b>FsRtlCheckUpperOplock</b> will always set this to NULL. 

</dd>
</dl>

### -param PrePendIrpRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if <b>FsRtlCheckUpperOplock</b> will return STATUS_PENDING. This parameter is optional and can be <b>NULL</b>. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
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
</table></span></div>



### -param Context

A context information pointer that was passed in the <i>CompletionRoutineContext</i> parameter to <b>FsRtlCheckUpperOplock</b>. 


### -param Irp

A optional pointer to the IRP for the I/O operation. <b>FsRtlCheckUpperOplock</b> will always set this to NULL.

</dd>
</dl>

### -param Flags [in]

A bitmask for the associated file I/O operation. A file system or filter driver sets bits to specify the behavior of <b>FsRtlCheckUpperOplock</b>. The <i>Flags</i> parameter has the following options:




### -param OPLOCK_UPPER_FLAG_CHECK_NO_BREAK   (0x00010000)

Return STATUS_CANNOT_BREAK_OPLOCK if the value of <i>NewLowerOplockState</i> results in any oplock break.


### -param OPLOCK_UPPER_FLAG_NOTIFY_REFRESH_READ   (0x00020000)

Break only Read (R) upper oplocks and notify R holders that they may again request R.  All other upper oplock checks it will return STATUS_CANNOT_BREAK_OPLOCK.

</dd>
</dl>

## -returns
<b>FsRtlCheckUpperOplock</b> returns an appropriate NTSTATUS code such as one of the following: 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>An oplock break is not required or the break was acknowledged. If <i>CompletionRoutine</i> is <b>NULL</b>, <b>FsRtlCheckUpperOplock</b> blocks while the oplock break is processed rather than return STATUS_PENDING.
<dl>
<dt><b>STATUS_CANNOT_BREAK_OPLOCK</b></dt>
</dl>The oplock break cannot be accomplished. See <i>Flags</i> for conditions that restrict a break.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>An opportunistic lock break is underway. If supplied, <i>PrePendIrpRoutine</i> is called as a notification of the pending operation.  <i>CompletionRoutine</i> is called when the oplock break is complete. STATUS_PENDING is a success code. 

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckoplockex~r5.md">FsRtlCheckOplockEx</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlupperoplockfsctrl~r4.md">FsRtlUpperOplockFsctrl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCheckUpperOplock routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

