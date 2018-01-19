---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockBreakToNoneEx~r5
title: FsRtlOplockBreakToNoneEx function
author: windows-driver-content
description: The FsRtlOplockBreakToNoneEx routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key.
old-location: ifsk\fsrtloplockbreaktononeex.htm
old-project: ifsk
ms.assetid: 229d4f31-7c3f-4ae2-bb67-d31c67121f61
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlOplockBreakToNoneEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlOplockBreakToNoneEx routine is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlOplockBreakToNoneEx
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
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlOplockBreakToNoneEx function



## -description
The <b>FsRtlOplockBreakToNoneEx</b> routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. 



## -syntax

````
NTSTATUS FsRtlOplockBreakToNoneEx(
  _Inout_  POPLOCK                       Oplock,
  _In_     PIRP                          Irp,
  _In_     ULONG                         Flags,
  _In_opt_ PVOID                         Context,
  _In_opt_ POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine,
  _In_opt_ POPLOCK_FS_PREPOST_IRP        PostIrpRoutine
);
````


## -parameters

### -param Oplock [in, out]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 


### -param Irp [in]

A pointer to the IRP for the I/O operation. 


### -param Flags [in]

A bitmask for the associated file I/O operation. A file system or filter driver sets bits to specify the behavior of <b>FsRtlOplockBreakToNoneEx</b>. The <i>Flags</i> parameter has the following options:




### -param OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001)

Specifies to allow an oplock break to proceed without blocking or pending the operation that caused the oplock break. Typically, this flag is only used if the IRP that the <i>Irp</i> parameter points to declares an IRP_MJ_CREATE operation. 

</dd>
</dl>

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




### -param Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlOplockBreakToNoneEx</b>. 


### -param Irp

A pointer to the IRP for the I/O operation. 

</dd>
</dl>

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



### -param Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlOplockBreakToNoneEx</b>. 


### -param Irp

A pointer to the IRP for the I/O operation. 

</dd>
</dl>

## -returns
<b>FsRtlOplockBreakToNoneEx</b> returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following: 
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>The IRP was canceled. STATUS_CANCELLED is an error code. 
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>An oplock break is underway. Therefore, the IRP was pended. STATUS_PENDING is a success code. 
<dl>
<dt><b>STATUS_OPLOCK_BREAK_IN_PROGRESS</b></dt>
</dl>An opportunistic lock break (oplock) is underway. STATUS_OPLOCK_BREAK_IN_PROGRESS is a success code that <b>FsRtlOplockBreakToNoneEx</b> returns if the caller set OPLOCK_FLAG_COMPLETE_IF_OPLOCKED in the <i>Flags</i> parameter and an oplock must be broken. 

 


## -remarks
For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltoplockbreaktononeex.md">FltOplockBreakToNoneEx</a> instead of <b>FsRtlOplockBreakToNoneEx</b>. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltoplockbreaktononeex.md">FltOplockBreakToNoneEx</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlOplockBreakToNoneEx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

