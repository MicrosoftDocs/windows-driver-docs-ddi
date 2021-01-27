---
UID: NF:fltkernel.FltSetStreamHandleContext
title: FltSetStreamHandleContext function (fltkernel.h)
description: The FltSetStreamHandleContext routine sets a context for a stream handle.
old-location: ifsk\fltsetstreamhandlecontext.htm
tech.root: ifsk
ms.date: 01/15/2021
keywords: ["FltSetStreamHandleContext function"]
ms.keywords: FltApiRef_p_to_z_371045bc-91b4-4695-a44a-7ef4fd5c1bd7.xml, FltSetStreamHandleContext, FltSetStreamHandleContext routine [Installable File System Drivers], fltkernel/FltSetStreamHandleContext, ifsk.fltsetstreamhandlecontext
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available nor supported on Windows 2000 SP4 and earlier operating systems.
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltSetStreamHandleContext
 - fltkernel/FltSetStreamHandleContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSetStreamHandleContext
---

# FltSetStreamHandleContext function

## -description

The **FltSetStreamHandleContext** routine sets a context for a stream handle.

## -parameters

### -param Instance

[in] An opaque instance pointer for the minifilter driver instance whose context is to be inserted into, removed from, or replaced in the list of contexts attached to the stream handle.

### -param FileObject

[in] A pointer to a [file object](../wdm/ns-wdm-_file_object.md) for the file stream. This parameter is required and cannot be **NULL**.

### -param Operation

[in] A flag that specifies details of the operation to be performed. This parameter must be one of the following:

| Value | Meaning |
| ----- | ------- |
| FLT_SET_CONTEXT_REPLACE_IF_EXISTS | If a context is already set for this *Instance*, replace it with *NewContext*. Otherwise, insert *NewContext* into the list of contexts for the stream handle. |
| FLT_SET_CONTEXT_KEEP_IF_EXISTS | If a context is already set for this *Instance*, return STATUS_FLT_CONTEXT_ALREADY_DEFINED. Otherwise, insert *NewContext* into the list of contexts for the stream handle. |

### -param NewContext

[in] A pointer to the new context to be set for the stream handle. This parameter is required and cannot be **NULL**.

### -param OldContext

[out, optional] A pointer to a caller-allocated variable that receives the address of the existing stream handle context for the *Instance* parameter. This parameter is optional and can be **NULL**. (For more information about this parameter, see the following Remarks section.)

## -returns

The **FltSetStreamHandleContext** routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following error codes:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_CONTEXT_ALREADY_DEFINED | If FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for *Operation*, this error code indicates that a context is already attached to the stream handle. |
| STATUS_FLT_CONTEXT_ALREADY_LINKED | The context that *NewContext* points to is already linked to an object.  In other words, this error code indicates that *NewContext* is already in use due to a successful prior call of a **FltSet*Xxx*Context** routine. |
| STATUS_FLT_DELETING_OBJECT | The specified *Instance* is being torn down. |
| STATUS_INVALID_PARAMETER | An invalid parameter was passed. For example, the *NewContext* parameter does not point to a valid stream handle context, or an invalid value was specified for *Operation*. |
| STATUS_NOT_SUPPORTED | An unsupported situation occurred, such as the file system does not support per-stream contexts for this file stream, or the caller provided a NULL *FileObject*. |

## -remarks

The **FltSetStreamHandleContext** routine adds, removes, or replaces a context for a minifilter driver instance on a stream handle. A minifilter driver can attach one context per minifilter driver instance to the stream handle.

A successful call to **FltSetStreamHandleContext** increments the reference count on *NewContext*. When the context pointed to by *NewContext* is no longer needed, the minifilter must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to decrement its reference count.

If **FltSetStreamHandleContext** fails, the reference count remains unchanged. In this case, the filter calling **FltSetStreamHandleContext** must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) for the *NewContext* object that was allocated and referenced in [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md). If **FltSetStreamHandleContext** fails and if the *OldContext* parameter is not **NULL** and does not point to NULL_CONTEXT then *OldContext* is a referenced pointer to the context currently associated with the transaction. The filter calling **FltSetStreamHandleContext** must call **FltReleaseContext** for *OldContext* as well.

Note that the *OldContext* pointer returned by **FltSetStreamHandleContext** must also be released by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) when it is no longer needed. For more information, see [Setting Contexts](/windows-hardware/drivers/ifs/setting-contexts) and [Releasing Contexts](/windows-hardware/drivers/ifs/releasing-contexts).

Also note that **FltSetStreamHandleContext** cannot be called on an unopened *FileObject*. Hence **FltSetStreamHandleContext** cannot be called from a pre-create callback for a stream because the stream has not been opened at that point. A minifilter can, however, allocate and set up the stream handle context in the pre-create callback, pass it to the post-create callback using the completion context parameter and set the stream handle context on the stream in the post-create callback.

To get a stream handle context, call [**FltGetStreamHandleContext**](nf-fltkernel-fltgetstreamhandlecontext.md).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To delete a stream handle context, call [**FltDeleteStreamHandleContext**](nf-fltkernel-fltdeletestreamhandlecontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

For more information about context reference counting, see [Referencing Contexts](/windows-hardware/drivers/ifs/referencing-contexts).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteStreamHandleContext**](nf-fltkernel-fltdeletestreamhandlecontext.md)

[**FltGetStreamHandleContext**](nf-fltkernel-fltgetstreamhandlecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)
