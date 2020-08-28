---
UID: NF:fltkernel.FltGetIoPriorityHint
title: FltGetIoPriorityHint function (fltkernel.h)
description: The FltGetIoPriorityHint routine is used by a minifilter driver to get IO priority information from Callback Data.
old-location: ifsk\fltgetiopriorityhint.htm
tech.root: ifsk
ms.assetid: 51c2068b-3dde-4e63-985c-51b8f7020948
ms.date: 04/16/2018
keywords: ["FltGetIoPriorityHint function"]
ms.keywords: FltApiRef_e_to_o_55aba7ac-700d-4cca-9ad1-abf80293041d.xml, FltGetIoPriorityHint, FltGetIoPriorityHint routine [Installable File System Drivers], fltkernel/FltGetIoPriorityHint, ifsk.fltgetiopriorityhint
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows operating systems.
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
 - FltGetIoPriorityHint
 - fltkernel/FltGetIoPriorityHint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetIoPriorityHint
---

# FltGetIoPriorityHint function


## -description

The <b>FltGetIoPriorityHint</b> routine is used by a minifilter driver to get IO priority information from Callback Data.

## -parameters

### -param Data 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure that represents an I/O operation. This parameter is required and cannot be <b>NULL</b>.

## -returns

The <b>FltGetIoPriorityHint</b> routine returns an IO priority hint retrieved from a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure.

## -remarks

The <b>FltGetIoPriorityHint</b> routine retrieves an IO Priority hint from the <i>Data</i><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure.  This hint will be based on the following fields in the <b>FLT_CALLBACK_DATA</b>:

<ul>
<li>
IRP (optional)  

</li>
<li>
FileObject  

</li>
<li>
Thread  

</li>
</ul>
If these <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> fields do not have an IO priority, the routine returns IoPriorityNormal.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintothread">FltSetIoPriorityHintIntoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_io_priority_info">IO_PRIORITY_INFO</a>

