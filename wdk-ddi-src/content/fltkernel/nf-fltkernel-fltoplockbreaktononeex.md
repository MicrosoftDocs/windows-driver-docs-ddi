---
UID: NF:fltkernel.FltOplockBreakToNoneEx
title: FltOplockBreakToNoneEx function
author: windows-driver-content
description: The FltOplockBreakToNoneEx routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key.
old-location: ifsk\fltoplockbreaktononeex.htm
old-project: ifsk
ms.assetid: 748951e3-9642-4c98-a3b0-5f6b18519bd4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_7111d712-59f1-4c71-b02c-9bb415aa118f.xml, FltOplockBreakToNoneEx, FltOplockBreakToNoneEx routine [Installable File System Drivers], fltkernel/FltOplockBreakToNoneEx, ifsk.fltoplockbreaktononeex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltOplockBreakToNoneEx routine is available starting with Windows 7.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltOplockBreakToNoneEx
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltOplockBreakToNoneEx function


## -description


The <b>FltOplockBreakToNoneEx</b> routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. 


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>. 


### -param CallbackData [in]

A pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


### -param Flags [in]

A bitmask for the associated file I/O operation. A minifilter driver sets bits to specify the behavior of <b>FltOplockBreakToNoneEx</b>. The <i>Flags</i> parameter has the following options: 





#### OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001)

Allows an oplock break to proceed without blocking or pending the operation that caused the oplock break. Typically, this flag is only used if the I/O operation that is represented by the callback data that the <i>CallbackData</i> parameter points to is an IRP_MJ_CREATE operation. 


### -param Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that the <i>WaitCompletionRoutine</i> and <i>PrePostCallbackDataRoutine </i>parameters point to. 


### -param WaitCompletionRoutine [in, optional]

A pointer to a caller-supplied callback routine. If an oplock break is in progress, this routine is called when the break is completed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the caller is put into a wait state until the oplock break is completed. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLTOPLOCK_WAIT_COMPLETE_ROUTINE) (
    __in PFLT_CALLBACK_DATA CallbackData,
 __in_opt PVOID Context
      );</pre>
</td>
</tr>
</table></span></div>
This routine has the following parameters: 





#### CallbackData

A pointer to the callback data structure for the I/O operation. 



#### Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FltOplockBreakToNoneEx</b>. 


### -param PrePostCallbackDataRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if the I/O operation is to be pended. The routine is called before the oplock package pends the IRP. This parameter is optional and can be <b>NULL</b>. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLTOPLOCK_PREPOST_CALLBACKDATA_ROUTINE) (
    __in PFLT_CALLBACK_DATA CallbackData,
 __in_opt PVOID Context
      );</pre>
</td>
</tr>
</table></span></div>
This routine has the following parameters: 





#### CallbackData

A pointer to the callback data structure for the I/O operation. 



#### Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FltOplockBreakToNoneEx</b>. 


## -returns



<b>FltOplockBreakToNoneEx</b> returns one of the following FLT_PREOP_CALLBACK_STATUS codes: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_COMPLETE</b></dt>
</dl>
</td>
<td width="60%">
<b>FltOplockBreakToNoneEx</b> encountered a pool allocation failure, or a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547108">FsRtlOplockBreakToNoneEx</a> function returned an error. <b>FltOplockBreakToNoneEx</b> will set the error code in the <b>Status</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure. The IO_STATUS_BLOCK structure is specified in the <b>IoStatus</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> callback data structure. The <i>CallbackData</i> parameter points to this FLT_CALLBACK_DATA. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_PENDING</b></dt>
</dl>
</td>
<td width="60%">
An oplock break was initiated, which caused the Filter Manager to post the I/O operation to a work queue. The I/O operation is represented by the callback data that the <i>CallbackData</i> parameter points to. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_SUCCESS_WITH_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
The callback data that the <i>CallbackData</i> parameter points to was not pended, and the I/O operation was performed immediately. Be aware that if the caller specified OPLOCK_FLAG_COMPLETE_IF_OPLOCKED in the <i>Flags</i> parameter, an oplock break might actually be in progress even though the I/O operation was not pended. To determine whether this is the situation, the caller should check for STATUS_OPLOCK_BREAK_IN_PROGRESS in the <b>Status</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure. The IO_STATUS_BLOCK structure is specified in the <b>IoStatus</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> callback data structure. 

</td>
</tr>
</table>
 




## -remarks



For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547108">FsRtlOplockBreakToNoneEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>
 

 

