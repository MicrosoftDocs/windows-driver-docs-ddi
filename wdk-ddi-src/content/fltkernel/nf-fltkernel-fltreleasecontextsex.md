---
UID: NF:fltkernel.FltReleaseContextsEx
title: FltReleaseContextsEx function (fltkernel.h)
description: FltReleaseContextsEx releases each context in a given FLT_RELATED_CONTEXTS_EX structure.
old-location: ifsk\fltreleasecontextsex.htm
tech.root: ifsk
ms.assetid: AC0811C9-8746-40F4-801E-6A1567ABDE0B
ms.date: 04/16/2018
ms.keywords: FltReleaseContextsEx, FltReleaseContextsEx routine [Installable File System Drivers], fltkernel/FltReleaseContextsEx, ifsk.fltreleasecontextsex
ms.topic: function
f1_keywords:
 - "fltkernel/FltReleaseContextsEx"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
- FltReleaseContextsEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltReleaseContextsEx function


## -description


<b>FltReleaseContextsEx</b> releases each context in a given <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a> structure.


## -parameters




### -param ContextsSize [in]

The size, in bytes, of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a> structure pointed to by <i>Contexts</i>. Set to <b>sizeof</b>(FLT_RELATED_CONTEXTS_EX).


### -param Contexts [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a> structure. 


## -returns



None 




## -remarks



<b>FltReleaseContextsEx</b> decrements the reference count on all contexts in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a> structure and sets all members of the structure to NULL_CONTEXT. 

To get the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a> structure for a given minifilter driver for a given I/O request, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetcontextsex">FltGetContextsEx</a>. 

For more information about context reference counting, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/referencing-contexts">Referencing Contexts</a>. 

Callers of <b>FltReleaseContextsEx</b> must be running at IRQL <= DISPATCH_LEVEL if all contexts were allocated from nonpaged pool. If any contexts were allocated from paged pool, callers must be running at IRQL <= APC_LEVEL. 

When each context's reference count reaches zero, the context is freed immediately if the caller is running at IRQL <= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetcontextsex">FltGetContextsEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>
 

 

