---
UID: NF:rxprocs.FsRtlCheckOplock
title: FsRtlCheckOplock macro
author: windows-driver-content
description: The FsRtlCheckOplock routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state.
old-location: ifsk\fsrtlcheckoplock.htm
old-project: ifsk
ms.assetid: e1430ef2-fb94-4f0d-bdc8-59b423fe9c8c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, FsRtlCheckOplock, FsRtlCheckOplock routine [Installable File System Drivers], O, R, c, e, fsrtlref_c11dbb80-c7a8-437d-bb6b-661edcf2f24a.xml, h, ifsk.fsrtlcheckoplock, k, l, o, p, rxprocs/FsRtlCheckOplock, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: rxprocs.h
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlCheckOplock
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# FsRtlCheckOplock macro


## -description


The <b>FsRtlCheckOplock</b> routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state. 


## -syntax


````
NTSTATUS FsRtlCheckOplock(
  _In_     POPLOCK                       Oplock,
  _In_     PIRP                          Irp,
  _In_opt_ PVOID                         Context,
  _In_opt_ POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine,
  _In_opt_ POPLOCK_FS_PREPOST_IRP        PostIrpRoutine
);
````


## -parameters




### -param A1

TBD


### -param A2

TBD


### -param A3

TBD


### -param A4

TBD


### -param A5

TBD






#### - Oplock [in]

An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 


#### - Irp [in]

A pointer to the IRP for the I/O operation. 


#### - Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that the <i>CompletionRoutine</i> and <i>PostIrpRoutine </i>parameters point to. 


#### - CompletionRoutine [in, optional]

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


##### - CompletionRoutine.Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlCheckOplock</b>. 


##### - CompletionRoutine.Irp

A pointer to the IRP for the I/O operation. 


#### - PostIrpRoutine [in, optional]

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


##### - PostIrpRoutine.Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlCheckOplock</b>. 


##### - PostIrpRoutine.Irp

A pointer to the IRP for the I/O operation. 


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

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltcheckoplock.md">FltCheckOplock</a> instead of <b>FsRtlCheckOplock</b>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md">FsRtlCurrentBatchOplock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md">FsRtlUninitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md">FsRtlOplockIsFastIoPossible</a>



<a href="..\fltkernel\nf-fltkernel-fltcheckoplock.md">FltCheckOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl~r2.md">FsRtlOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCheckOplock routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

