---
UID: NF:fltkernel.FltReleaseContexts
title: FltReleaseContexts function (fltkernel.h)
description: FltReleaseContexts releases each context in a given FLT_RELATED_CONTEXTS structure.
old-location: ifsk\fltreleasecontexts.htm
tech.root: ifsk
ms.assetid: 9b6a28ad-f86c-475b-adee-8d2d8b2d6d61
ms.date: 04/16/2018
keywords: ["FltReleaseContexts function"]
ms.keywords: FltApiRef_p_to_z_697bebdc-a3c6-4d95-a97d-0de7b819d56f.xml, FltReleaseContexts, FltReleaseContexts function [Installable File System Drivers], fltkernel/FltReleaseContexts, ifsk.fltreleasecontexts
f1_keywords:
 - "fltkernel/FltReleaseContexts"
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltReleaseContexts
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltReleaseContexts function


## -description


<b>FltReleaseContexts</b> releases each context in a given <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a> structure. 


## -parameters




### -param Contexts [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a> structure. 


## -returns



None 




## -remarks



<b>FltReleaseContexts</b> decrements the reference count on all contexts in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a> structure and sets all members of the structure to NULL_CONTEXT. 

To get the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a> structure for a given minifilter driver for a given I/O request, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetcontexts">FltGetContexts</a>. 

For more information about context reference counting, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/referencing-contexts">Referencing Contexts</a>. 

Callers of <b>FltReleaseContexts</b> must be running at IRQL <= DISPATCH_LEVEL if all contexts were allocated from nonpaged pool. If any contexts were allocated from paged pool, callers must be running at IRQL <= APC_LEVEL. 

When each context's reference count reaches zero, the context is freed immediately if the caller is running at IRQL <= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetcontexts">FltGetContexts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>
 

 

