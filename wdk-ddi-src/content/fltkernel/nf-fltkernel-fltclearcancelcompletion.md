---
UID: NF:fltkernel.FltClearCancelCompletion
title: FltClearCancelCompletion function (fltkernel.h)
description: FltClearCancelCompletion clears a cancel routine that was specified for an I/O operation.
old-location: ifsk\fltclearcancelcompletion.htm
tech.root: ifsk
ms.assetid: 75c66cb7-3378-4951-9180-d1bd9f201a42
ms.date: 04/16/2018
keywords: ["FltClearCancelCompletion function"]
ms.keywords: FltApiRef_a_to_d_4dea0214-a0a2-45b8-b044-960881a8f065.xml, FltClearCancelCompletion, FltClearCancelCompletion routine [Installable File System Drivers], fltkernel/FltClearCancelCompletion, ifsk.fltclearcancelcompletion
f1_keywords:
 - "fltkernel/FltClearCancelCompletion"
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
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltClearCancelCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltClearCancelCompletion function


## -description


<b>FltClearCancelCompletion</b> clears a cancel routine that was specified for an I/O operation. 


## -parameters




### -param CallbackData [in]

Pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


## -returns



If no cancel routine was previously set or if IRP cancellation is already in progress, <b>FltClearCancelCompletion</b> returns STATUS_CANCELLED. Otherwise, it returns STATUS_SUCCESS. 




## -remarks



A minifilter driver calls <b>FltClearCancelCompletion</b> to clear a cancel routine that was specified for an I/O operation by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a>. The operation must be an IRP-based I/O operation. To determine whether a given callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure represents an IRP-based I/O operation, use the <a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro. 

To cancel an I/O operation, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a>
 

 

