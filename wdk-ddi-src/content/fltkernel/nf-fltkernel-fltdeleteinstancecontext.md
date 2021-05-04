---
UID: NF:fltkernel.FltDeleteInstanceContext
title: FltDeleteInstanceContext function (fltkernel.h)
description: FltDeleteInstanceContext removes a context from a given instance and marks the context for deletion.
old-location: ifsk\fltdeleteinstancecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltDeleteInstanceContext function"]
ms.keywords: FltApiRef_a_to_d_2ccc7fef-0bff-4df4-b617-fb4749bb3ed6.xml, FltDeleteInstanceContext, FltDeleteInstanceContext function [Installable File System Drivers], fltkernel/FltDeleteInstanceContext, ifsk.fltdeleteinstancecontext
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
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltDeleteInstanceContext
 - fltkernel/FltDeleteInstanceContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDeleteInstanceContext
---

# FltDeleteInstanceContext function

## -description

**FltDeleteInstanceContext** removes a context from a given instance and marks the context for deletion.

## -parameters

### -param Instance

[in] Opaque instance pointer for the instance.

### -param OldContext

[out] Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be **NULL**. If *OldContext* is not **NULL** and does not point to NULL_CONTEXT, the caller is responsible for calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to release this context when it is no longer needed.

## -returns

**FltDeleteInstanceContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The specified *Instance* is being torn down. This is an error code. |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as **FltDeleteInstanceContext** to explicitly delete a context.

A minifilter driver calls **FltDeleteInstanceContext** to remove a context from an instance and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To get an instance context, call [**FltGetInstanceContext**](nf-fltkernel-fltgetinstancecontext.md).

To set an instance context, call [**FltSetInstanceContext**](nf-fltkernel-fltsetinstancecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltGetInstanceContext**](nf-fltkernel-fltgetinstancecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetInstanceContext**](nf-fltkernel-fltsetinstancecontext.md)
