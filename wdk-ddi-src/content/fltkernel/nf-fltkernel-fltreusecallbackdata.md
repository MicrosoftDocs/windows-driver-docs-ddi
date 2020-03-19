---
UID: NF:fltkernel.FltReuseCallbackData
title: FltReuseCallbackData function (fltkernel.h)
description: The FltReuseCallbackData routine reinitializes a callback data structure so that it can be reused.
old-location: ifsk\fltreusecallbackdata.htm
tech.root: ifsk
ms.assetid: c8671ba7-6128-4f0f-b5b1-32ce35e31168
ms.date: 04/16/2018
keywords: ["FltReuseCallbackData function"]
ms.keywords: FltApiRef_p_to_z_a412f56d-8cee-40de-93fb-1c007fe87c3c.xml, FltReuseCallbackData, FltReuseCallbackData routine [Installable File System Drivers], fltkernel/FltReuseCallbackData, ifsk.fltreusecallbackdata
f1_keywords:
 - "fltkernel/FltReuseCallbackData"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltReuseCallbackData
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltReuseCallbackData function


## -description


The <b>FltReuseCallbackData</b> routine reinitializes a callback data structure so that it can be reused. 


## -parameters




### -param CallbackData [in, out]

Pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure to be reused. This structure must have been allocated by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a>. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



<b>FltReuseCallbackData</b> reinitializes a callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure so that it can be used in a new I/O operation. <b>FltReuseCallbackData</b> does not change the <b>TargetInstance</b> field or the <b>TargetFileObject</b> field of the callback data structure's I/O parameter block. 

The <b>FltReuseCallbackData</b> routine frees any <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> chain associated with the supplied <i>CallbackData</i> object. A pointer to an MDL chain associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> object will be invalid after a call to <b>FltReuseCallbackData</b> for that object.

Using <b>FltReuseCallbackData</b> to reuse a callback data structure is faster than freeing the structure and allocating a new one. 

A minifilter driver should use <b>FltReuseCallbackData</b> only on a callback data structure that the minifilter driver previously allocated with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a> and used in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>. 

If the callback data structure was used for asynchronous I/O, the minifilter driver should not call <b>FltReuseCallbackData</b> until the <i>CallbackRoutine</i> specified in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a> is called. 

In particular, a minifilter driver should not use this routine for any callback data structures not allocated by the minifilter driver itself. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata">FltFreeCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreissuesynchronousio">FltReissueSynchronousIo</a>
 

 

