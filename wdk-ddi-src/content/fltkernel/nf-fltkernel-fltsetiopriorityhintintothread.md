---
UID: NF:fltkernel.FltSetIoPriorityHintIntoThread
title: FltSetIoPriorityHintIntoThread function (fltkernel.h)
description: The FltSetIoPriorityHintIntoThread routine is used by a minifilter driver to set the IO priority information in a thread.
old-location: ifsk\fltsetiopriorityhintintothread.htm
tech.root: ifsk
ms.assetid: 924fadbe-2703-43f8-985c-db5a7bb960a6
ms.date: 04/16/2018
keywords: ["FltSetIoPriorityHintIntoThread function"]
ms.keywords: FltApiRef_p_to_z_acdf2d2e-c98e-4e7d-8074-fb2b89594771.xml, FltSetIoPriorityHintIntoThread, FltSetIoPriorityHintIntoThread routine [Installable File System Drivers], fltkernel/FltSetIoPriorityHintIntoThread, ifsk.fltsetiopriorityhintintothread
f1_keywords:
 - "fltkernel/FltSetIoPriorityHintIntoThread"
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows Vista.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltSetIoPriorityHintIntoThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSetIoPriorityHintIntoThread function


## -description


The <b>FltSetIoPriorityHintIntoThread</b> routine is used by a minifilter driver to set the IO priority information in a thread.


## -parameters




### -param Thread [in]

A pointer to the thread to modify. This parameter is required and cannot be <b>NULL</b>. 


### -param PriorityHint [in]

The  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a> enumeration value to set for the thread information pointed to by <i>Thread</i>.


## -returns



If the IO Priority value passed to the <i>PriorityHint</i> parameter is successfully applied to the <i>Thread</i>, <b>FltSetIoPriorityHintIntoThread</b> returns STATUS_SUCCESS. Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>PriorityHint</i> parameter is invalid. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



This routine is NONPAGED and can be called from paging IO paths.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhint">FltGetIoPriorityHint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a>
 

 

