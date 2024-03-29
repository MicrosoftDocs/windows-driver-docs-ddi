---
UID: NF:fltkernel.FltReleaseContext
title: FltReleaseContext function (fltkernel.h)
description: FltReleaseContext decrements the reference count on a context.
old-location: ifsk\fltreleasecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltReleaseContext function"]
ms.keywords: FltApiRef_p_to_z_1040d19b-2ecb-4229-adda-b73f5c2bc828.xml, FltReleaseContext, FltReleaseContext function [Installable File System Drivers], fltkernel/FltReleaseContext, ifsk.fltreleasecontext
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
 - FltReleaseContext
 - fltkernel/FltReleaseContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltReleaseContext
---

# FltReleaseContext function

## -description

**FltReleaseContext** decrements the reference count on a context.

## -parameters

### -param Context [in]

Pointer to the context. Must be a valid pointer to a context object for a volume, instance, stream, or stream handle. This parameter is required and cannot be **NULL**.

## -returns

None

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

A minifilter driver calls **FltReleaseContext** to release a context. **FltReleaseContext** decrements the reference count on the given context. When the reference count reaches zero, the context is freed immediately if the caller is running at IRQL <= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context.

> [!NOTE]
> After **FltReleaseContext** returns, the caller must not use the context, because the context might have already been freed.

Every successful call to [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md), **FltGet***Xxx***Context**, or [**FltReferenceContext**](nf-fltkernel-fltreferencecontext.md) must eventually be matched by a call to **FltReleaseContext**.

Note that the *OldContext* pointer returned by **FltSet***Xxx***Context** and the *Context* parameter that is used to call [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md) must also be released by calling **FltReleaseContext** when they are no longer needed.

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To increment the reference count on a context, call [**FltReferenceContext**](./nf-fltkernel-fltreferencecontext.md).

For more information about context reference counting, see [Referencing Contexts](/windows-hardware/drivers/ifs/referencing-contexts).

Callers of **FltReleaseContext** must be running at IRQL <= DISPATCH_LEVEL if the context was allocated from nonpaged pool. If the context was allocated from paged pool, callers must be running at IRQL <= APC_LEVEL.

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltGetContexts**](./nf-fltkernel-fltgetcontexts.md)

[**FltGetContextsEx**](./nf-fltkernel-fltgetcontextsex.md)

[**FltGetFileContext**](./nf-fltkernel-fltgetfilecontext.md)

[**FltGetInstanceContext**](./nf-fltkernel-fltgetinstancecontext.md)

[**FltGetSectionContext**](./nf-fltkernel-fltgetsectioncontext.md)

[**FltGetStreamContext**](./nf-fltkernel-fltgetstreamcontext.md)

[**FltGetStreamHandleContext**](./nf-fltkernel-fltgetstreamhandlecontext.md)

[**FltGetTransactionContext**](./nf-fltkernel-fltgettransactioncontext.md)

[**FltGetVolumeContext**](./nf-fltkernel-fltgetvolumecontext.md)

[**FltReferenceContext**](./nf-fltkernel-fltreferencecontext.md)

[**FltReleaseContexts**](./nf-fltkernel-fltreleasecontexts.md)

[**FltSetFileContext**](./nf-fltkernel-fltsetfilecontext.md)

[**FltSetInstanceContext**](./nf-fltkernel-fltsetinstancecontext.md)

[**FltSetStreamContext**](./nf-fltkernel-fltsetstreamcontext.md)

[**FltSetStreamHandleContext**](./nf-fltkernel-fltsetstreamhandlecontext.md)

[**FltSetTransactionContext**](./nf-fltkernel-fltsettransactioncontext.md)

[**FltSetVolumeContext**](./nf-fltkernel-fltsetvolumecontext.md)
