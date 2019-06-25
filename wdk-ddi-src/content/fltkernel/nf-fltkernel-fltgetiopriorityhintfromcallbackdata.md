---
UID: NF:fltkernel.FltGetIoPriorityHintFromCallbackData
title: FltGetIoPriorityHintFromCallbackData function (fltkernel.h)
description: The FltGetIoPriorityHintFromCallbackData routine is used by a minifilter driver to get IO priority information from callback data.
old-location: ifsk\fltgetiopriorityhintfromcallbackdata.htm
tech.root: ifsk
ms.assetid: feb3428c-ab18-4bd5-bf8a-81c7aaab0413
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_ce313b29-9c88-47f7-9a7f-a4ad9945ade1.xml, FltGetIoPriorityHintFromCallbackData, FltGetIoPriorityHintFromCallbackData routine [Installable File System Drivers], fltkernel/FltGetIoPriorityHintFromCallbackData, ifsk.fltgetiopriorityhintfromcallbackdata
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetIoPriorityHintFromCallbackData
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetIoPriorityHintFromCallbackData function


## -description


The <b>FltGetIoPriorityHintFromCallbackData</b> routine is used by a minifilter driver to get IO priority information from callback data.


## -parameters




### -param Data [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure that represents an I/O operation. This parameter is required and cannot be <b>NULL</b>. 


## -returns



The <b>FltGetIoPriorityHintFromCallbackData</b> routine returns an IO priority hint retrieved from the <i>Data</i><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure. 

If the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure does not have an IO priority, the routine returns IoPriorityNormal.

If an error occurs retrieving the hint, the routine returns IoPriorityNormal.




## -remarks



This routine is NONPAGED and can be called from paging IO paths.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetiopriorityhint">FltGetIoPriorityHint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetiopriorityhintintothread">FltSetIoPriorityHintIntoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_io_priority_info">IO_PRIORITY_INFO</a>
 

 

