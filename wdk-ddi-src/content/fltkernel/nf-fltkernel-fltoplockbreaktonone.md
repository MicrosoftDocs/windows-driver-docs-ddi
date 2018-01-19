---
UID: NF:fltkernel.FltOplockBreakToNone
title: FltOplockBreakToNone function
author: windows-driver-content
description: The FltOplockBreakToNone routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key.
old-location: ifsk\fltoplockbreaktonone.htm
old-project: ifsk
ms.assetid: 212dc455-9317-4901-9a96-1c71dde0faf3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltOplockBreakToNone
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltOplockBreakToNone routine is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltOplockBreakToNone
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
req.typenames: EXpsFontRestriction
---

# FltOplockBreakToNone function



## -description
The <b>FltOplockBreakToNone</b> routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. 



## -syntax

````
FLT_PREOP_CALLBACK_STATUS FltOplockBreakToNone(
  _In_     POPLOCK                                 Oplock,
  _In_     PFLT_CALLBACK_DATA                      CallbackData,
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




### -param CallbackData

A pointer to the callback data structure for the I/O operation. 


### -param Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FltOplockBreakToNone</b>. 

</dd>
</dl>

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




### -param CallbackData

A pointer to the callback data structure for the I/O operation. 


### -param Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FltOplockBreakToNone</b>. 

</dd>
</dl>

## -returns
<b>FltOplockBreakToNone</b> returns one of the following FLT_PREOP_CALLBACK_STATUS codes: 
<dl>
<dt><b>FLT_PREOP_COMPLETE</b></dt>
</dl><b>FltOplockBreakToNone</b> encountered a pool allocation failure, or a call to the <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockbreaktononeex~r5.md">FsRtlOplockBreakToNoneEx</a> function returned an error. <b>FltOplockBreakToNone</b> will set the error code in the <b>Status</b> member of the <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure of the <b>IoStatus</b> member. The IO_STATUS_BLOCK structure is specified in the <b>IoStatus</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> callback data structure. The <i>CallbackData</i> parameter points to this FLT_CALLBACK_DATA. 
<dl>
<dt><b>FLT_PREOP_PENDING</b></dt>
</dl>An oplock break was initiated, which caused the Filter Manager to post the I/O operation to a work queue. The I/O operation is represented by the callback data that the <i>CallbackData</i> parameter points to. 
<dl>
<dt><b>FLT_PREOP_SUCCESS_WITH_CALLBACK</b></dt>
</dl>The callback data that the <i>CallbackData</i> parameter points to was not pended, and the I/O operation was performed immediately. 

 


## -remarks
For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockbreaktononeex~r5.md">FsRtlOplockBreakToNoneEx</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltOplockBreakToNone routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

