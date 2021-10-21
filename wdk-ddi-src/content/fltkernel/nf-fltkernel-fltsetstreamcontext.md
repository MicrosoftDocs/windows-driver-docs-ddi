---
UID: NF:fltkernel.FltSetStreamContext
title: FltSetStreamContext function (fltkernel.h)
description: The FltSetStreamContext routine sets a context for a file stream.
old-location: ifsk\fltsetstreamcontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltSetStreamContext function"]
ms.keywords: FltApiRef_p_to_z_b304d975-533c-4794-aabc-e706fed09893.xml, FltSetStreamContext, FltSetStreamContext routine [Installable File System Drivers], fltkernel/FltSetStreamContext, ifsk.fltsetstreamcontext
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems.
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
 - FltSetStreamContext
 - fltkernel/FltSetStreamContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSetStreamContext
---

# FltSetStreamContext function

## -description

The **FltSetStreamContext** routine sets a context for a file stream.

## -parameters

### -param Instance [in]

An opaque instance pointer for the minifilter driver instance whose context is to be inserted into, removed from, or replaced in the list of contexts attached to the file stream.

### -param FileObject [in]

A pointer to a [file object](../wdm/ns-wdm-_file_object.md) for the file stream.

### -param Operation [in]

Flag specifying details of the operation to be performed. This parameter must be one of the following:

| Flag | Meaning |
| ---- | ------- |
| FLT_SET_CONTEXT_REPLACE_IF_EXISTS | If a context is already set for *Instance*, **FltSetStreamContext** will replace it with the context specified in *NewContext*. Otherwise, it will insert *NewContext* into the list of contexts for the file stream. |
| FLT_SET_CONTEXT_KEEP_IF_EXISTS | If a context is already set for this *Instance*, **FltSetStreamContext** will return STATUS_FLT_CONTEXT_ALREADY_DEFINED, and will not replace the existing context or increment the reference count. If a context has not already been set, the routine will insert *NewContext* into the list of contexts for the file stream and increment the reference count. |

### -param NewContext [in]

A pointer to the new context to be set for the file stream. This parameter is required and cannot be **NULL**.

### -param OldContext [out]

A pointer to a caller-allocated variable that receives the address of the existing stream context for the *Instance* parameter, if one is already set. This parameter is optional and can be **NULL**. For more information about this parameter, see the following Remarks section.

## -returns

The **FltSetStreamContext** routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_CONTEXT_ALREADY_DEFINED | If FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for *Operation*, this error code indicates that a stream context is already attached to the file stream. |
| STATUS_FLT_CONTEXT_ALREADY_LINKED | The context pointed to by the *NewContext* parameter is already linked to an object.  In other words, this error code indicates that *NewContext* is already in use due to a successful prior call of a **FltSet***Xxx***Context** routine. |
| STATUS_FLT_DELETING_OBJECT | The instance specified in the *Instance* parameter is being torn down. This is an error code. |
| STATUS_INVALID_PARAMETER | An invalid parameter was passed. For example, the *NewContext* parameter does not point to a valid stream context, or an invalid value was specified for the *Operation* parameter. This is an error code. |
| STATUS_NOT_SUPPORTED | The file system does not support per-stream contexts for this file stream. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

A minifilter driver calls **FltSetStreamContext** to attach a stream context to a file stream, or to remove or replace an existing stream context. A minifilter driver can attach one context per minifilter driver instance to the file stream.

**FltSetStreamContext** cannot be called on an unopened *FileObject*. Hence it cannot be called from a pre-create callback for a stream because the stream has not been opened at that point. A minifilter driver can, however, allocate and set up the stream context in the pre-create callback, pass it to the post-create callback using the completion context parameter and set the stream context on the stream in the post-create callback.

### Reference Counting

If **FltSetStreamContext** succeeds:

- The reference count on *NewContext* is incremented. When *NewContext* is no longer needed, the minifilter must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to decrement its reference count.

Else if **FltSetStreamContext** fails:

- The reference count on *NewContext* remains unchanged.
- If *OldContext* is not **NULL** and does not point to NULL_CONTEXT then *OldContext* is a referenced pointer to the context currently associated with the stream. The filter calling **FltSetStreamContext** must call **FltReleaseContext** for *OldContext* as well when the context pointer is no longer needed.

Regardless of success:

- The filter calling **FltSetStreamContext** must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to decrement the reference count on the *NewContext* object that was incremented by [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

For more information, see [Referencing Contexts](/windows-hardware/drivers/ifs/referencing-contexts).

### Other context operations

For more information, see [Setting Contexts](/windows-hardware/drivers/ifs/setting-contexts), and [Releasing Contexts](/windows-hardware/drivers/ifs/releasing-contexts):

- To determine whether stream contexts are supported for a given file, call [**FltSupportsStreamContexts**](nf-fltkernel-fltsupportsstreamcontexts.md)

- To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

- To get a stream context, call [**FltGetStreamContext**](nf-fltkernel-fltgetstreamcontext.md).

- To delete a stream context, call [**FltDeleteStreamContext**](nf-fltkernel-fltdeletestreamcontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteStreamContext**](nf-fltkernel-fltdeletestreamcontext.md)

[**FltGetStreamContext**](nf-fltkernel-fltgetstreamcontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)
