---
UID: NF:fltkernel.FltOplockBreakH
title: FltOplockBreakH function
author: windows-driver-content
description: The FltOplockBreakH routine breaks CACHE_HANDLE_LEVEL opportunistic locks (oplocks).
old-location: ifsk\fltoplockbreakh.htm
old-project: ifsk
ms.assetid: 1341c0c6-f943-4f94-8535-8b6cc7b5c27e
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltOplockBreakH routine [Installable File System Drivers], ifsk.fltoplockbreakh, fltkernel/FltOplockBreakH, FltApiRef_e_to_o_55fd17fd-a64a-4837-a000-0d51685e5a18.xml, FltOplockBreakH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltOplockBreakH routine is available starting with Windows 7.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltOplockBreakH
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltOplockBreakH function


## -description


The <b>FltOplockBreakH</b> routine breaks CACHE_HANDLE_LEVEL opportunistic locks (oplocks). 


## -syntax


````
FLT_PREOP_CALLBACK_STATUS FltOplockBreakH(
  _In_     POPLOCK                                 Oplock,
  _In_     PFLT_CALLBACK_DATA                      CallbackData,
  _In_     ULONG                                   Flags,
  _In_opt_ PVOID                                   Context,
  _In_opt_ PFLTOPLOCK_WAIT_COMPLETE_ROUTINE        WaitCompletionRoutine,
  _In_opt_ PFLTOPLOCK_PREPOST_CALLBACKDATA_ROUTINE PrePostCallbackDataRoutine
);
````


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>. 


### -param CallbackData [in]

A pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


### -param Flags [in]

A bitmask for the associated file I/O operation. A minifilter driver sets bits to specify the behavior of <b>FltOplockBreakH</b>. The <i>Flags</i> parameter has the following options:





#### OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001)

Allows an oplock break to proceed without blocking or pending the operation that caused the oplock break. 



#### OPLOCK_FLAG_IGNORE_OPLOCK_KEYS (0x00000008)

Allows CACHE_HANDLE_LEVEL oplock breaks to proceed regardless of the oplock key. 


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

A context information pointer that was passed in the <i>Context</i> parameter to <b>FltOplockBreakH</b>. 


### -param PrePostCallbackDataRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if the I/O operation must be pended. The routine is called before the oplock package pends the IRP. This parameter is optional and can be <b>NULL</b>. 

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

A context information pointer that was passed in the <i>Context</i> parameter to <b>FltOplockBreakH</b>. 


## -returns



<b>FltOplockBreakH</b> returns one of the following FLT_PREOP_CALLBACK_STATUS codes: 

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
<b>FltOplockBreakH</b> encountered a pool allocation failure, or a call to the <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockbreakh~r5.md">FsRtlOplockBreakH</a> function returned an error. <b>FltOplockBreakH</b> will set the error code in the <b>Status</b> member of the <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure. The IO_STATUS_BLOCK structure is specified in the <b>IoStatus</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> callback data structure. The <i>CallbackData</i> parameter points to this FLT_CALLBACK_DATA. 

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
The callback data that the <i>CallbackData</i> parameter points to was not pended, and the I/O operation was performed immediately. Be aware that if the caller specified OPLOCK_FLAG_COMPLETE_IF_OPLOCKED in the <i>Flags</i> parameter, an oplock break might actually be in progress even though the I/O operation was not pended. To determine whether this is the situation, the caller should check for STATUS_OPLOCK_BREAK_IN_PROGRESS in the <b>Status</b> member of the <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure. The IO_STATUS_BLOCK structure is specified in the <b>IoStatus</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> callback data structure. 

</td>
</tr>
</table>
 




## -remarks



For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockbreakh~r5.md">FsRtlOplockBreakH</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>



<a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltOplockBreakH routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

