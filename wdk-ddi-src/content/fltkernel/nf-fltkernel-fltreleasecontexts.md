---
UID: NF:fltkernel.FltReleaseContexts
title: FltReleaseContexts function (fltkernel.h)
description: FltReleaseContexts releases each context in a given FLT_RELATED_CONTEXTS structure.
old-location: ifsk\fltreleasecontexts.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltReleaseContexts function"]
ms.keywords: FltApiRef_p_to_z_697bebdc-a3c6-4d95-a97d-0de7b819d56f.xml, FltReleaseContexts, FltReleaseContexts function [Installable File System Drivers], fltkernel/FltReleaseContexts, ifsk.fltreleasecontexts
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltReleaseContexts
 - fltkernel/FltReleaseContexts
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltReleaseContexts
---

# FltReleaseContexts function

## -description

**FltReleaseContexts** releases each context in a given [**FLT_RELATED_CONTEXTS**](ns-fltkernel-_flt_related_contexts.md) structure.

## -parameters

### -param Contexts

[in] Pointer to the [**FLT_RELATED_CONTEXTS**](ns-fltkernel-_flt_related_contexts.md) structure.

## -returns

None

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

**FltReleaseContexts** decrements the reference count on all contexts in the [**FLT_RELATED_CONTEXTS**](ns-fltkernel-_flt_related_contexts.md) structure and sets all members of the structure to NULL_CONTEXT.

To get the **FLT_RELATED_CONTEXTS** structure for a given minifilter driver for a given I/O request, call [**FltGetContexts**](./nf-fltkernel-fltgetcontexts.md).

For more information about context reference counting, see [Referencing Contexts](/windows-hardware/drivers/ifs/referencing-contexts).

Callers of **FltReleaseContexts** must be running at IRQL <= DISPATCH_LEVEL if all contexts were allocated from nonpaged pool. If any contexts were allocated from paged pool, callers must be running at IRQL <= APC_LEVEL.

When each context's reference count reaches zero, the context is freed immediately if the caller is running at IRQL <= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context.

## -see-also

[**FLT_CONTEXT_REGISTRATION**](ns-fltkernel-_flt_context_registration.md)

[**FLT_RELATED_CONTEXTS**](ns-fltkernel-_flt_related_contexts.md)

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltGetContexts**](./nf-fltkernel-fltgetcontexts.md)

[**FltReleaseContext**](./nf-fltkernel-fltreleasecontext.md)

[**FltReleaseContextsEx**](./nf-fltkernel-fltreleasecontextsex.md)