---
UID: NF:fltkernel.FltGetIoPriorityHintFromThread
title: FltGetIoPriorityHintFromThread function (fltkernel.h)
description: The FltGetIoPriorityHintFromThread routine is used by a minifilter driver to get IO priority information from a thread.
old-location: ifsk\fltgetiopriorityhintfromthread.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltGetIoPriorityHintFromThread function"]
ms.keywords: FltApiRef_e_to_o_edc8f8c5-8be8-45a7-9936-c2146e5fd4b6.xml, FltGetIoPriorityHintFromThread, FltGetIoPriorityHintFromThread routine [Installable File System Drivers], fltkernel/FltGetIoPriorityHintFromThread, ifsk.fltgetiopriorityhintfromthread
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetIoPriorityHintFromThread
 - fltkernel/FltGetIoPriorityHintFromThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetIoPriorityHintFromThread
---

# FltGetIoPriorityHintFromThread function


## -description

The <b>FltGetIoPriorityHintFromThread</b> routine is used by a minifilter driver to get IO priority information from a thread.

## -parameters

### -param Thread 

[in]
A pointer to the thread from which to retrieve priority information. This parameter is required and cannot be <b>NULL</b>.

## -returns

The <b>FltGetIoPriorityHintFromThread</b> routine returns an IO priority hint retrieved from a thread.

If <i>Thread</i> does not have a priority, the routine returns IoPriorityNormal.




If an error occurs retrieving the priority, the routine returns IoPriorityNormal.

## -remarks

This routine is NONPAGED and can be called from paging IO paths.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhint">FltGetIoPriorityHint</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintothread">FltSetIoPriorityHintIntoThread</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_io_priority_info">IO_PRIORITY_INFO</a>
