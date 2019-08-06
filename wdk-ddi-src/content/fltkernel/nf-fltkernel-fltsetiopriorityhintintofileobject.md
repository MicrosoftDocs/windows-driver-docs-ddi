---
UID: NF:fltkernel.FltSetIoPriorityHintIntoFileObject
title: FltSetIoPriorityHintIntoFileObject function (fltkernel.h)
description: The FltSetIoPriorityHintIntoFileObject routine is used by a minifilter driver to set the I/O priority information in a file object.
old-location: ifsk\fltsetiopriorityhintintofileobject.htm
tech.root: ifsk
ms.assetid: 95a56ca3-e223-49ec-9151-bedb3f3597c3
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_981cae2b-b29c-4890-a462-163031a668d3.xml, FltSetIoPriorityHintIntoFileObject, FltSetIoPriorityHintIntoFileObject routine [Installable File System Drivers], fltkernel/FltSetIoPriorityHintIntoFileObject, ifsk.fltsetiopriorityhintintofileobject
ms.topic: function
f1_keywords:
 - "fltkernel/FltSetIoPriorityHintIntoFileObject"
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
- FltSetIoPriorityHintIntoFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSetIoPriorityHintIntoFileObject function


## -description


The <b>FltSetIoPriorityHintIntoFileObject</b> routine is used by a minifilter driver to set the I/O priority information in a file object.


## -parameters




### -param FileObject [in]

A pointer to the file object to modify. This parameter is required and cannot be <b>NULL</b>. 


### -param PriorityHint [in]

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a> enumeration value to set for the file object pointed to by <i>FileObject</i>.


## -returns



If the I/O priority value passed in the <i>PriorityHint</i> parameter is successfully applied to the <i>FileObject</i> structure, <b>FltSetIoPriorityHintIntoFileObject</b> returns STATUS_SUCCESS. Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

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



This routine is NONPAGED and can be called from paging I/O paths.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetiopriorityhint">FltGetIoPriorityHint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetiopriorityhintintothread">FltSetIoPriorityHintIntoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a>
 

 

