---
UID: NF:fltkernel.FltDeleteFileContext
title: FltDeleteFileContext function (fltkernel.h)
description: The FltDeleteFileContext routine retrieves and deletes a file context that a given minifilter driver has set for a given file.
old-location: ifsk\fltdeletefilecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltDeleteFileContext function"]
ms.keywords: FltApiRef_a_to_d_53ae4cfc-b70a-405d-b947-cb0f04d4663b.xml, FltDeleteFileContext, FltDeleteFileContext routine [Installable File System Drivers], fltkernel/FltDeleteFileContext, ifsk.fltdeletefilecontext
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista and later
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
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltDeleteFileContext
 - fltkernel/FltDeleteFileContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDeleteFileContext
---

# FltDeleteFileContext function

## -description

The **FltDeleteFileContext** routine retrieves and deletes a file context that a given minifilter driver has set for a given file.

## -parameters

### -param Instance

[in] Opaque instance pointer for the caller. This parameter is required and cannot be **NULL**.

### -param FileObject

[in] File object pointer for the file. This parameter is required and cannot be **NULL**.

### -param OldContext

[out] Pointer to a caller-allocated variable that receives the address of the deleted context. If no matching context is found, this variable receives NULL_CONTEXT. This parameter is optional and can be **NULL**. For more information about this parameter, see the following Remarks section.

## -returns

**FltDeleteFileContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |
| STATUS_NOT_SUPPORTED | File contexts are not supported for this file. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as **FltDeleteFileContext** or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md) to explicitly delete a context.

A minifilter driver calls **FltDeleteFileContext** to retrieve and delete a file context that it previously set for a file by calling [**FltSetFileContext**](nf-fltkernel-fltsetfilecontext.md).

If the *OldContext* parameter is **NULL** on input and a matching file context is found, **FltDeleteFileContext** releases the reference that was added by the minifilter driver's previous call to [**FltSetFileContext**](nf-fltkernel-fltsetfilecontext.md). The deleted context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread).

If the *OldContext* parameter is not **NULL** and a matching file context is found and returned, the caller is responsible for releasing the reference that was added by [**FltSetFileContext**](nf-fltkernel-fltsetfilecontext.md). To release this reference, the minifilter driver must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) on the deleted file context as soon as possible after performing any necessary cleanup.

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To determine whether file contexts are supported for a given file, call [**FltSupportsFileContexts**](nf-fltkernel-fltsupportsfilecontexts.md) or [**FltSupportsFileContextsEx**](nf-fltkernel-fltsupportsfilecontextsex.md).

## -see-also

[**FLT_CONTEXT_REGISTRATION**](ns-fltkernel-_flt_context_registration.md)

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltGetFileContext**](nf-fltkernel-fltgetfilecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetFileContext**](nf-fltkernel-fltsetfilecontext.md)

[**FltSupportsFileContexts**](nf-fltkernel-fltsupportsfilecontexts.md)

[**FltSupportsFileContextsEx**](nf-fltkernel-fltsupportsfilecontextsex.md)
