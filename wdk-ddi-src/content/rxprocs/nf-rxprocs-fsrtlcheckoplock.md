---
UID: NF:rxprocs.FsRtlCheckOplock
title: FsRtlCheckOplock macro
author: windows-driver-content
description: The FsRtlCheckOplock routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state.
old-location: ifsk\fsrtlcheckoplock.htm
tech.root: ifsk
ms.assetid: e1430ef2-fb94-4f0d-bdc8-59b423fe9c8c
ms.date: 4/16/2018
ms.keywords: FsRtlCheckOplock, FsRtlCheckOplock routine [Installable File System Drivers], fsrtlref_c11dbb80-c7a8-437d-bb6b-661edcf2f24a.xml, ifsk.fsrtlcheckoplock, rxprocs/FsRtlCheckOplock
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlCheckOplock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlCheckOplock macro


## -description


The <b>FsRtlCheckOplock</b> routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state. 


## -parameters




### -param A1

<p>An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/Ff546150(v=VS.85).aspx"><b>FsRtlInitializeOplock</b></a>. </p>


### -param A2

<p>A pointer to the IRP for the I/O operation. </p>


### -param A3

<p>A pointer to caller-defined context information to be passed to the callback routines that the <i>CompletionRoutine</i> and <i>PostIrpRoutine </i>parameters point to. </p>


### -param A4

<p>A pointer to a caller-supplied callback routine. If an opportunistic lock break is in progress, this routine is called when the break is completed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the caller is put into a wait state until the opportunistic lock break is completed. </p>
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
(*POPLOCK_WAIT_COMPLETE_ROUTINE) (
      IN PVOID Context,
      IN PIRP Irp
      );</pre>
          </td>
        </tr>
      </table>
    </span>
  </div>
  <p>This routine has the following parameters: </p>
  <p></p>
  <dl>
    <dt>
      <a id="Context"></a>
      <a id="context"></a>
      <a id="CONTEXT"></a>
      <i>Context</i>
    </dt>
    
      <p>A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlCheckOplock</b>. </p>
    
    <dt>
      <a id="Irp"></a>
      <a id="irp"></a>
      <a id="IRP"></a>
      <i>Irp</i>
    </dt>
    
      <p>A pointer to the IRP for the I/O operation. </p>
    
  </dl>


### -param A5

<p>A pointer to a caller-supplied callback routine to be called if the I/O operation is posted to a work queue. This parameter is optional and can be <b>NULL</b>. </p>
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
      IN PVOID Context,
      IN PIRP Irp
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
    
      <p>A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlCheckOplock</b>. </p>
    
    <dt>
      <a id="Irp"></a>
      <a id="irp"></a>
      <a id="IRP"></a>
      <i>Irp</i>
    </dt>
    
      <p>A pointer to the IRP for the I/O operation. </p>
    
  </dl>






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

Minifilters should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541844">FltCheckOplock</a> instead of <b>FsRtlCheckOplock</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541844">FltCheckOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545825">FsRtlCurrentBatchOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546150">FsRtlInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547112">FsRtlOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547120">FsRtlOplockIsFastIoPossible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547328">FsRtlUninitializeOplock</a>
 

 

