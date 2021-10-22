---
UID: NF:fltkernel.FltGetStreamHandleContext
title: FltGetStreamHandleContext function (fltkernel.h)
description: The FltGetStreamHandleContext routine retrieves a context that was set for a stream handle by a given minifilter driver instance.
old-location: ifsk\fltgetstreamhandlecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltGetStreamHandleContext function"]
ms.keywords: FltApiRef_e_to_o_4a329c48-3a48-47bc-b998-3aaee454fbef.xml, FltGetStreamHandleContext, FltGetStreamHandleContext routine [Installable File System Drivers], fltkernel/FltGetStreamHandleContext, ifsk.fltgetstreamhandlecontext
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
 - FltGetStreamHandleContext
 - fltkernel/FltGetStreamHandleContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetStreamHandleContext
---

# FltGetStreamHandleContext function

## -description

The **FltGetStreamHandleContext** routine retrieves a context that was set for a stream handle by a given minifilter driver instance.

## -parameters

### -param Instance [in]

Opaque instance pointer for the minifilter driver instance whose context is to be retrieved.

### -param FileObject [in]

Pointer to a file object for the stream handle.

### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the context.

## -returns

**FltGetStreamHandleContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |
| STATUS_NOT_SUPPORTED | The file system does not support per-stream contexts for this file stream. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

**FltGetStreamHandleContext** retrieves a context that was set for a stream handle by a given minifilter driver.

**FltGetStreamHandleContext** increments the reference count on the context that the *Context* parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md). Thus every successful call to **FltGetStreamHandleContext** must be matched by a subsequent call to **FltReleaseContext**.

To set a context for a stream handle, call [**FltSetStreamHandleContext**](nf-fltkernel-fltsetstreamhandlecontext.md)

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To delete a stream handle context, call [**FltDeleteStreamHandleContext**](nf-fltkernel-fltdeletestreamhandlecontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteStreamHandleContext**](nf-fltkernel-fltdeletestreamhandlecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetStreamHandleContext**](nf-fltkernel-fltsetstreamhandlecontext.md)
