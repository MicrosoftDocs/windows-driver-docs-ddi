---
UID: NF:fltkernel.FltFreeCallbackData
title: FltFreeCallbackData function (fltkernel.h)
description: The FltFreeCallbackData routine frees a callback data structure allocated by the FltAllocateCallbackData routine.
old-location: ifsk\fltfreecallbackdata.htm
tech.root: ifsk
ms.assetid: 45cf398f-f7f0-4eb1-b490-4123c6c9f6fa
ms.date: 04/16/2018
keywords: ["FltFreeCallbackData function"]
ms.keywords: FltApiRef_e_to_o_1ad2fa09-dd36-4178-a422-a6a1f3854182.xml, FltFreeCallbackData, FltFreeCallbackData routine [Installable File System Drivers], fltkernel/FltFreeCallbackData, ifsk.fltfreecallbackdata
f1_keywords:
 - "fltkernel/FltFreeCallbackData"
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
- FltFreeCallbackData
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltFreeCallbackData function


## -description


The <b>FltFreeCallbackData</b> routine frees a callback data structure allocated by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a> routine. 


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure to be freed. This <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure must have been allocated by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a>. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



A minifilter driver should use <b>FltFreeCallbackData</b> only on a callback data structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) that it previously allocated with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a> and used in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a>. 

In particular, a minifilter driver should not use this routine for any callback data structures that were not allocated by the minifilter driver itself. 

The <b>FltFreeCallbackData</b> routine frees any <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> chain associated with the supplied <i>CallbackData</i> object. A pointer to an MDL chain associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> object will be invalid after a call to <b>FltFreeCallbackData</b> for that object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreusecallbackdata">FltReuseCallbackData</a>
 

 

