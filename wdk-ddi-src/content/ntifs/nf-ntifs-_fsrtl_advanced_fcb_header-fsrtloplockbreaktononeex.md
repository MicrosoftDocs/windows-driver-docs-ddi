---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockBreakToNoneEx
title: FsRtlOplockBreakToNoneEx function
author: windows-driver-content
description: The FsRtlOplockBreakToNoneEx routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key.
old-location: ifsk\fsrtloplockbreaktononeex.htm
tech.root: ifsk
ms.assetid: 229d4f31-7c3f-4ae2-bb67-d31c67121f61
ms.date: 04/16/2018
ms.keywords: FsRtlOplockBreakToNoneEx, FsRtlOplockBreakToNoneEx routine [Installable File System Drivers], fsrtlref_df3afc17-e57b-43b5-8281-4128854d2064.xml, ifsk.fsrtloplockbreaktononeex, ntifs/FsRtlOplockBreakToNoneEx
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlOplockBreakToNoneEx routine is available starting with Windows 7.
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
-	FsRtlOplockBreakToNoneEx
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlOplockBreakToNoneEx function


## -description


The <b>FsRtlOplockBreakToNoneEx</b> routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. 


## -parameters




### -param Oplock [in, out]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546150">FsRtlInitializeOplock</a>. 


### -param Irp [in]

A pointer to the IRP for the I/O operation. 


### -param Flags [in]

A bitmask for the associated file I/O operation. A file system or filter driver sets bits to specify the behavior of <b>FsRtlOplockBreakToNoneEx</b>. The <i>Flags</i> parameter has the following options:





#### OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001)

Specifies to allow an oplock break to proceed without blocking or pending the operation that caused the oplock break. Typically, this flag is only used if the IRP that the <i>Irp</i> parameter points to declares an IRP_MJ_CREATE operation. 


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

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlOplockBreakToNoneEx</b>. 



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

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlOplockBreakToNoneEx</b>. 



#### Irp

A pointer to the IRP for the I/O operation. 


## -returns



<b>FsRtlOplockBreakToNoneEx</b> returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following: 

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
An oplock break is underway. Therefore, the IRP was pended. STATUS_PENDING is a success code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OPLOCK_BREAK_IN_PROGRESS</b></dt>
</dl>
</td>
<td width="60%">
An opportunistic lock break (oplock) is underway. STATUS_OPLOCK_BREAK_IN_PROGRESS is a success code that <b>FsRtlOplockBreakToNoneEx</b> returns if the caller set OPLOCK_FLAG_COMPLETE_IF_OPLOCKED in the <i>Flags</i> parameter and an oplock must be broken. 

</td>
</tr>
</table>
 




## -remarks



For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543392">FltOplockBreakToNoneEx</a> instead of <b>FsRtlOplockBreakToNoneEx</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543392">FltOplockBreakToNoneEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546150">FsRtlInitializeOplock</a>
 

 

