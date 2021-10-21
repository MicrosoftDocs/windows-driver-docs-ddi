---
UID: NF:fltkernel.FltDeleteContext
title: FltDeleteContext function (fltkernel.h)
description: FltDeleteContext marks a specified context for deletion.
old-location: ifsk\fltdeletecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltDeleteContext function"]
ms.keywords: FltApiRef_a_to_d_d4c075e6-7a69-4d2f-9017-eccbf55eb9e0.xml, FltDeleteContext, FltDeleteContext function [Installable File System Drivers], fltkernel/FltDeleteContext, ifsk.fltdeletecontext
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
 - FltDeleteContext
 - fltkernel/FltDeleteContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltDeleteContext
---

# FltDeleteContext function

## -description

**FltDeleteContext** marks a specified context for deletion.

## -parameters

### -param Context [in]

A pointer to the context to delete. This parameter is required and cannot be **NULL**.

## -returns

None.

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine, such as **FltDeleteContext**, to explicitly delete a context.

**FltDeleteContext** marks a context for deletion. The context is usually freed as soon as the current reference on it is released, unless there is an outstanding reference on it (for example, because the context is still being used by another thread).

You should consider the following items when you use **FltDeleteContext**:

* When a minifilter driver calls **FltDeleteContext**, the minifilter driver must already have a reference to the context. However, when the minifilter driver calls [FltDeleteStreamHandleContext](nf-fltkernel-fltdeletestreamhandlecontext.md), [FltDeleteStreamContext](nf-fltkernel-fltdeletestreamcontext.md), [FltDeleteInstanceContext](nf-fltkernel-fltdeleteinstancecontext.md), and so on, the minifilter driver does not require a reference to the context. After the minifilter driver calls **FltDeleteContext**, that reference to the context is still valid. The minifilter driver must call the [FltReleaseContext](nf-fltkernel-fltreleasecontext.md) routine to release the reference to the context.

* **FltDeleteContext** removes the context from the internal filter manager structures. Then, further calls to functions that get contexts, such as  [**FltGetContexts**](nf-fltkernel-fltgetcontexts.md) and [**FltGetInstanceContext**](nf-fltkernel-fltgetinstancecontext.md), cannot locate that context. However, the context memory is not released until the reference count for the context goes to 0.

Contexts can also be deleted by calling the appropriate delete-context routine from the following table.

| Context Type | Delete-Context Routine |
| ------------ | ---------------------- |
| FLT_FILE_CONTEXT | [FltDeleteFileContext](nf-fltkernel-fltdeletefilecontext.md) (Windows Vista and later only.) |
| FLT_INSTANCE_CONTEXT | [FltDeleteInstanceContext](nf-fltkernel-fltdeleteinstancecontext.md) |
| FLT_SECTION_CONTEXT | [FltCloseSectionForDataScan](nf-fltkernel-fltclosesectionfordatascan.md) (Windows 8 and later only.) |
| FLT_STREAM_CONTEXT | [FltDeleteStreamContext](nf-fltkernel-fltdeletestreamcontext.md) |
| FLT_STREAMHANDLE_CONTEXT | [FltDeleteStreamHandleContext](nf-fltkernel-fltdeletestreamhandlecontext.md) |
| FLT_TRANSACTION_CONTEXT | [FltDeleteTransactionContext](nf-fltkernel-fltdeletetransactioncontext.md) (Windows Vista and later only.) |
| FLT_VOLUME_CONTEXT | [FltDeleteVolumeContext](nf-fltkernel-fltdeletevolumecontext.md) |

To allocate a new context, call [FltAllocateContext](nf-fltkernel-fltallocatecontext.md).

To increment the reference count on a context, call [FltReferenceContext](nf-fltkernel-fltreferencecontext.md).

To decrement the reference count on a context, call [FltReleaseContext](nf-fltkernel-fltreleasecontext.md).

A section context, FLT_SECTION_CONTEXT type, must not be deleted using **FltDeleteContext**. Instead, use  [FltReleaseContext](nf-fltkernel-fltreleasecontext.md) to deallocate a section context.

## -see-also

[FltAllocateContext](nf-fltkernel-fltallocatecontext.md)

[FltCloseSectionForDataScan](nf-fltkernel-fltclosesectionfordatascan.md)

[FltDeleteFileContext](nf-fltkernel-fltdeletefilecontext.md)

[FltDeleteInstanceContext](nf-fltkernel-fltdeleteinstancecontext.md)

[FltDeleteStreamContext](nf-fltkernel-fltdeletestreamcontext.md)

[FltDeleteStreamHandleContext](nf-fltkernel-fltdeletestreamhandlecontext.md)

[FltDeleteTransactionContext](nf-fltkernel-fltdeletetransactioncontext.md)

[FltDeleteVolumeContext](nf-fltkernel-fltdeletevolumecontext.md)

[FltReferenceContext](nf-fltkernel-fltreferencecontext.md)

[FltReleaseContext](nf-fltkernel-fltreleasecontext.md)
