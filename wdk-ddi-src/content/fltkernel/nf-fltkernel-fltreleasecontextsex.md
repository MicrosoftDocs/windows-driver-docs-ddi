---
UID: NF:fltkernel.FltReleaseContextsEx
title: FltReleaseContextsEx function (fltkernel.h)
description: FltReleaseContextsEx releases each context in a given FLT_RELATED_CONTEXTS_EX structure.
old-location: ifsk\fltreleasecontextsex.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltReleaseContextsEx function"]
ms.keywords: FltReleaseContextsEx, FltReleaseContextsEx routine [Installable File System Drivers], fltkernel/FltReleaseContextsEx, ifsk.fltreleasecontextsex
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltReleaseContextsEx
 - fltkernel/FltReleaseContextsEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltReleaseContextsEx
---

# FltReleaseContextsEx function

## -description

**FltReleaseContextsEx** releases each context in a given [**FLT_RELATED_CONTEXTS_EX**](ns-fltkernel-_flt_related_contexts_ex.md) structure.

## -parameters

### -param ContextsSize

[in] The size, in bytes, of the [**FLT_RELATED_CONTEXTS_EX**](ns-fltkernel-_flt_related_contexts_ex.md) structure pointed to by *Contexts*. Set to **sizeof**(FLT_RELATED_CONTEXTS_EX).

### -param Contexts

[in] Pointer to the [**FLT_RELATED_CONTEXTS_EX**](ns-fltkernel-_flt_related_contexts_ex.md) structure.

## -returns

None

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

**FltReleaseContextsEx** decrements the reference count on all contexts in the [**FLT_RELATED_CONTEXTS_EX**](ns-fltkernel-_flt_related_contexts_ex.md) structure and sets all members of the structure to NULL_CONTEXT.

To get the [**FLT_RELATED_CONTEXTS_EX**](ns-fltkernel-_flt_related_contexts_ex.md) structure for a given minifilter driver for a given I/O request, call [**FltGetContextsEx**](./nf-fltkernel-fltgetcontextsex.md).

For more information about context reference counting, see [Referencing Contexts](/windows-hardware/drivers/ifs/referencing-contexts).

Callers of **FltReleaseContextsEx** must be running at IRQL <= DISPATCH_LEVEL if all contexts were allocated from nonpaged pool. If any contexts were allocated from paged pool, callers must be running at IRQL <= APC_LEVEL.

When each context's reference count reaches zero, the context is freed immediately if the caller is running at IRQL <= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context.

## -see-also

[**FLT_CONTEXT_REGISTRATION**](ns-fltkernel-_flt_context_registration.md)

[**FLT_RELATED_CONTEXTS_EX**](ns-fltkernel-_flt_related_contexts_ex.md)

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltGetContextsEx**](./nf-fltkernel-fltgetcontextsex.md)

[**FltReleaseContext**](./nf-fltkernel-fltreleasecontext.md)