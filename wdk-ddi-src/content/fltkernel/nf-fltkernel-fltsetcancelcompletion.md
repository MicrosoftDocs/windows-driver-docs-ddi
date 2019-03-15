---
UID: NF:fltkernel.FltSetCancelCompletion
title: FltSetCancelCompletion function (fltkernel.h)
description: A minifilter driver calls FltSetCancelCompletion to specify a cancel routine to be called if a given I/O operation is canceled.
old-location: ifsk\fltsetcancelcompletion.htm
tech.root: ifsk
ms.assetid: 3f15d3b2-321d-45ca-8fe4-d8706fe61d48
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_36fb8e4e-a50b-4b9c-a208-9d6189f5b5a7.xml, FltSetCancelCompletion, FltSetCancelCompletion routine [Installable File System Drivers], fltkernel/FltSetCancelCompletion, ifsk.fltsetcancelcompletion
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltSetCancelCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSetCancelCompletion function


## -description


A minifilter driver calls <b>FltSetCancelCompletion</b> to specify a cancel routine to be called if a given I/O operation is canceled. 


## -parameters




### -param CallbackData [in]

Pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the I/O operation. The operation must be an IRP-based I/O operation and must not be a paging I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. This parameter is required and cannot be <b>NULL</b>. 


### -param CanceledCallback [in]

Pointer to a caller-supplied cancel routine. The Filter Manager calls this routine if the I/O operation represented by <i>CallbackData</i> is canceled. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_COMPLETE_CANCELED_CALLBACK) (
      IN PFLT_CALLBACK_DATA CallbackData
      );</pre>
</td>
</tr>
</table></span></div>




#### CallbackData

Pointer to the FLT_CALLBACK_DATA structure for the I/O operation. 


## -returns



<b>FltSetCancelCompletion</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value. 




## -remarks



<b>FltSetCancelCompletion</b> specifies a cancel routine for an IRP-based I/O operation that is to be posted to a work queue. 

Minifilter drivers usually call <b>FltSetCancelCompletion</b> for an I/O operation immediately before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543449">FltQueueDeferredIoWorkItem</a> to post the operation to a work queue. 

Do not call <b>FltSetCancelCompletion</b> for any I/O operation that is to be posted to a cancel-safe callback data queue using the <b>FltCbdq</b><i>Xxx</i> routines. 

The Filter Manager calls the <i>CanceledCallback</i> routine without holding the system cancel spin lock or performing any other synchronization. Any required synchronization must be supplied by the minifilter driver itself. 

To cancel an I/O operation, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541785">FltCancelIo</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541785">FltCancelIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541857">FltClearCancelCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543449">FltQueueDeferredIoWorkItem</a>
 

 

