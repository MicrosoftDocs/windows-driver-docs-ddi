---
UID: NF:fltkernel.FltGetStreamContext
title: FltGetStreamContext function (fltkernel.h)
description: Learn more about the FltGetStreamContext function.
old-location: ifsk\fltgetstreamcontext.htm
tech.root: ifsk
ms.date: 04/25/2023
keywords: ["FltGetStreamContext function"]
ms.keywords: FltApiRef_e_to_o_e7a12c32-5aec-433e-86e4-46844f56e75a.xml, FltGetStreamContext, FltGetStreamContext routine [Installable File System Drivers], fltkernel/FltGetStreamContext, ifsk.fltgetstreamcontext
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetStreamContext
 - fltkernel/FltGetStreamContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetStreamContext
---

# FltGetStreamContext function

## -description

The **FltGetStreamContext** routine retrieves a context that was set for a file stream by a given minifilter driver instance.

## -parameters

### -param Instance [in]

Opaque instance pointer for the minifilter driver instance whose context is to be retrieved.

### -param FileObject [in]

Pointer to a file object for the stream.

### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the context. This parameter is required and can't be set to NULL.

## -returns

**FltGetStreamContext** returns STATUS_SUCCESS when it successfully returns the requested stream context. Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |
| STATUS_NOT_SUPPORTED | The file system does not support per-stream contexts for this file stream. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

**FltGetStreamContext** retrieves a context that was set for a file stream by a given minifilter driver instance.

**FltGetStreamContext** increments the reference count on the context that the *Context* parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md). Thus every successful call to **FltGetStreamContext** must be matched by a subsequent call to **FltReleaseContext**.

To set a context for a file stream, call [**FltSetStreamContext**](nf-fltkernel-fltsetstreamcontext.md).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To delete a stream context, call [**FltDeleteStreamContext**](nf-fltkernel-fltdeletestreamcontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteStreamContext**](nf-fltkernel-fltdeletestreamcontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetStreamContext**](nf-fltkernel-fltsetstreamcontext.md)
