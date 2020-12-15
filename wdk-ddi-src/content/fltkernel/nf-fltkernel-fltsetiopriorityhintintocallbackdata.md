---
UID: NF:fltkernel.FltSetIoPriorityHintIntoCallbackData
title: FltSetIoPriorityHintIntoCallbackData function (fltkernel.h)
description: The FltSetIoPriorityHintIntoCallbackData routine is used by a minifilter driver to set the I/O priority information in callback data.
old-location: ifsk\fltsetiopriorityhintintocallbackdata.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltSetIoPriorityHintIntoCallbackData function"]
ms.keywords: FltApiRef_p_to_z_2d697ab8-c8ef-47f5-bfed-d0a82a61a1ef.xml, FltSetIoPriorityHintIntoCallbackData, FltSetIoPriorityHintIntoCallbackData routine [Installable File System Drivers], fltkernel/FltSetIoPriorityHintIntoCallbackData, ifsk.fltsetiopriorityhintintocallbackdata
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltSetIoPriorityHintIntoCallbackData
 - fltkernel/FltSetIoPriorityHintIntoCallbackData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSetIoPriorityHintIntoCallbackData
---

# FltSetIoPriorityHintIntoCallbackData function


## -description

The <b>FltSetIoPriorityHintIntoCallbackData</b> routine is used by a minifilter driver to set the I/O priority information in callback data.

## -parameters

### -param Data 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure that represents an I/O operation. This parameter is required and cannot be <b>NULL</b>.

### -param PriorityHint 

[in]
The <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a> enumeration value to set for the I/O operation in the callback data pointed to by <i>Data</i>.

## -returns

If this is a fast IO operation, the <b>FltSetIoPriorityHintIntoCallbackData</b> routine returns STATUS_SUCCESS.  

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
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

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhint">FltGetIoPriorityHint</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintothread">FltSetIoPriorityHintIntoThread</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a>
