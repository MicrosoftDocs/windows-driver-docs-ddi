---
UID: NF:fltkernel.FltCancelIo
title: FltCancelIo function (fltkernel.h)
description: The FltCancelIo routine cancels an I/O operation.
old-location: ifsk\fltcancelio.htm
tech.root: ifsk
ms.assetid: 30f2345d-6ed8-475f-879a-d3218039fded
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_e539a1bb-9dd4-4e1b-ac10-b5f742923839.xml, FltCancelIo, FltCancelIo routine [Installable File System Drivers], fltkernel/FltCancelIo, ifsk.fltcancelio
ms.topic: function
f1_keywords:
 - "fltkernel/FltCancelIo"
req.header: fltkernel.h
req.include-header: FltKernel.h
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
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltCancelIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCancelIo function


## -description


The <b>FltCancelIo</b> routine cancels an I/O operation. 


## -parameters




### -param CallbackData [in]

Pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


## -returns



<b>FltCancelIo</b> returns <b>TRUE</b> if the I/O operation was canceled successfully. Otherwise, it returns <b>FALSE</b>. 




## -remarks



A minifilter driver that initiates an I/O operation by calling a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a> can cancel the operation by calling <b>FltCancelIo</b>. The operation must be an IRP-based I/O operation, it must not be currently posted to the minifilter driver's own work queue, and it must not have been completed. 

If the IRP has a cancel routine, <b>FltCancelIo</b> sets the IRP's cancel bit and calls the cancel routine. 

If the IRP does not have a cancel routine, and therefore the IRP is not cancelable, <b>FltCancelIo</b> sets the IRP's cancel bit and returns <b>FALSE</b>. The IRP should be canceled at a later time when it becomes cancelable. 

If a minifilter driver that did not initiate the IRP-based I/O operation calls <b>FltCancelIo</b>, the results are unpredictable. For example, the IRP might be completed with a success NTSTATUS code even though its cancel bit was set. 

<b>FltCancelIo</b> returns <b>FALSE</b> if any of the following conditions are true: 

<ul>
<li>
The operation is not an IRP-based I/O operation. 

</li>
<li>
No cancel routine is specified for the I/O operation. 

</li>
<li>
The I/O operation has already been canceled. 

</li>
</ul>
To determine whether a given callback data structure represents an IRP-based I/O operation, use the FLT_IS_IRP_OPERATION macro. 

To specify a cancel routine for an I/O operation, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a>. 

To clear a cancel routine that was set for an I/O operation, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclearcancelcompletion">FltClearCancelCompletion</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclearcancelcompletion">FltClearCancelCompletion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>
 

 

