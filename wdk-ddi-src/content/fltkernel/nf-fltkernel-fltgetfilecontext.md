---
UID: NF:fltkernel.FltGetFileContext
title: FltGetFileContext function (fltkernel.h)
description: The FltGetFileContext routine retrieves a context that was set for a file by a given minifilter driver instance.
old-location: ifsk\fltgetfilecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltGetFileContext function"]
ms.keywords: FltApiRef_e_to_o_230a0040-01b0-4998-8f16-427eec529aee.xml, FltGetFileContext, FltGetFileContext routine [Installable File System Drivers], fltkernel/FltGetFileContext, ifsk.fltgetfilecontext
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows Vista and later.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetFileContext
 - fltkernel/FltGetFileContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetFileContext
---

# FltGetFileContext function

## -description

The **FltGetFileContext** routine retrieves a context that was set for a file by a given minifilter driver instance.

## -parameters

### -param Instance

[in] Opaque instance pointer for the caller. This parameter is required and cannot be **NULL**.

### -param FileObject

[in] File object pointer for the file. This parameter is required and cannot be **NULL**.

### -param Context

[out] Pointer to a caller-allocated variable that receives the address of the context. This parameter is required and cannot be **NULL**.

## -returns

**FltGetFileContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |
| STATUS_NOT_SUPPORTED | File contexts are not supported for this file. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

A minifilter driver calls **FltGetFileContext** to retrieve the file context that it has set for a given file.

**FltGetFileContext** increments the reference count on the context that the *Context* parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md). Thus, every successful call to **FltGetFileContext** must be matched by a subsequent call to **FltReleaseContext**.

To set a file context, call [**FltSetFileContext**](nf-fltkernel-fltsetfilecontext.md).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To delete a file context, call [**FltDeleteFileContext**](nf-fltkernel-fltdeletefilecontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

To determine whether file contexts are supported for a given file, call [**FltSupportsFileContexts**](nf-fltkernel-fltsupportsfilecontexts.md) or [**FltSupportsFileContextsEx**](nf-fltkernel-fltsupportsfilecontextsex.md).

## -see-also

[**FLT_CONTEXT_REGISTRATION**](ns-fltkernel-_flt_context_registration.md)

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteFileContext**](nf-fltkernel-fltdeletefilecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetFileContext**](nf-fltkernel-fltsetfilecontext.md)

[**FltSupportsFileContexts**](nf-fltkernel-fltsupportsfilecontexts.md)

[**FltSupportsFileContextsEx**](nf-fltkernel-fltsupportsfilecontextsex.md)
