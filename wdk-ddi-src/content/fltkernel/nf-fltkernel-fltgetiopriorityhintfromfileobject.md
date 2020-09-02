---
UID: NF:fltkernel.FltGetIoPriorityHintFromFileObject
title: FltGetIoPriorityHintFromFileObject function (fltkernel.h)
description: The FltGetIoPriorityHintFromFileObject routine is used by a minifilter driver to get IO priority information from a file object.
old-location: ifsk\fltgetiopriorityhintfromfileobject.htm
tech.root: ifsk
ms.assetid: ca854716-8f6e-42bd-ae03-e31f951b0874
ms.date: 04/16/2018
keywords: ["FltGetIoPriorityHintFromFileObject function"]
ms.keywords: FltApiRef_e_to_o_0a239f34-f16d-4386-a171-66c537e3f241.xml, FltGetIoPriorityHintFromFileObject, FltGetIoPriorityHintFromFileObject routine [Installable File System Drivers], fltkernel/FltGetIoPriorityHintFromFileObject, ifsk.fltgetiopriorityhintfromfileobject
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
 - FltGetIoPriorityHintFromFileObject
 - fltkernel/FltGetIoPriorityHintFromFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetIoPriorityHintFromFileObject
---

# FltGetIoPriorityHintFromFileObject function


## -description

The <b>FltGetIoPriorityHintFromFileObject</b> routine is used by a minifilter driver to get IO priority information from a file object.

## -parameters

### -param FileObject 

[in]
A pointer to a file object. This parameter is required and cannot be <b>NULL</b>.

## -returns

The <b>FltGetIoPriorityHintFromFileObject</b> routine returns an IO priority hint retrieved from a file object.

If the <i>FileObject</i> does not have a priority, the routine returns IoPriorityNormal.

If an error occurs retrieving the priority, the routine returns IoPriorityNormal.

## -remarks

This routine is NONPAGED and can be called from paging IO paths.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhint">FltGetIoPriorityHint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintothread">FltSetIoPriorityHintIntoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_io_priority_info">IO_PRIORITY_INFO</a>

