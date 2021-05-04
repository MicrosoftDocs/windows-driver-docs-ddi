---
UID: NF:fltkernel.FltDeleteStreamHandleContext
title: FltDeleteStreamHandleContext function (fltkernel.h)
description: FltDeleteStreamHandleContext removes a context that a given minifilter driver instance has set for a given stream handle and marks the context for deletion.
old-location: ifsk\fltdeletestreamhandlecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltDeleteStreamHandleContext function"]
ms.keywords: FltApiRef_a_to_d_445c2977-ef26-4cc6-9fb3-1873fbb976f2.xml, FltDeleteStreamHandleContext, FltDeleteStreamHandleContext function [Installable File System Drivers], fltkernel/FltDeleteStreamHandleContext, ifsk.fltdeletestreamhandlecontext
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
 - FltDeleteStreamHandleContext
 - fltkernel/FltDeleteStreamHandleContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltDeleteStreamHandleContext
---

# FltDeleteStreamHandleContext function

## -description

**FltDeleteStreamHandleContext** removes a context that a given minifilter driver instance has set for a given stream handle and marks the context for deletion.

## -parameters

### -param Instance

[in] Opaque instance pointer for the minifilter driver instance whose context is to be removed from the list of contexts attached to the stream handle.

### -param FileObject

[in] Pointer to a file object for the file stream.

### -param OldContext

[out] Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be **NULL**. If *OldContext* is not **NULL** and does not point to NULL_CONTEXT, the caller is responsible for calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to release this context when it is no longer needed.

## -returns

**FltDeleteStreamHandleContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The specified *Instance* is being torn down. This is an error code. |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |
| STATUS_NOT_SUPPORTED | The file system does not support per-stream contexts for this file stream handle. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as **FltDeleteStreamHandleContext** to explicitly delete a context.

A minifilter driver calls **FltDeleteStreamHandleContext** to remove a context from a stream handle and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still in use by another thread).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To get a stream context, call [**FltGetStreamHandleContext**](nf-fltkernel-fltgetstreamhandlecontext.md).

To set a stream context, call [**FltSetStreamHandleContext**](nf-fltkernel-fltsetstreamhandlecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltGetStreamHandleContext**](nf-fltkernel-fltgetstreamhandlecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetStreamHandleContext**](nf-fltkernel-fltsetstreamhandlecontext.md)
