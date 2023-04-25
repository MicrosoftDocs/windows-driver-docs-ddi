---
UID: NF:fltkernel.FltGetSectionContext
title: FltGetSectionContext function (fltkernel.h)
description: Learn more about the FltGetSectionContext function.
old-location: ifsk\fltgetsectioncontext.htm
tech.root: ifsk
ms.date: 04/25/2023
keywords: ["FltGetSectionContext function"]
ms.keywords: FltGetSectionContext, FltGetSectionContext routine [Installable File System Drivers], fltkernel/FltGetSectionContext, ifsk.fltgetsectioncontext
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
 - FltGetSectionContext
 - fltkernel/FltGetSectionContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetSectionContext
---

# FltGetSectionContext function

## -description

The **FltGetSectionContext** routine retrieves a section context that was created for a file stream by a specified minifilter driver instance.

## -parameters

### -param Instance [in]

An opaque instance pointer for the minifilter driver instance whose context is to be retrieved.

### -param FileObject [in]

A pointer to a file object for the stream.

### -param Context [out]

A pointer to a caller-allocated variable that receives the address of the context. This parameter is required and can't be set to NULL.

## -returns

**FltGetSectionContext** returns STATUS_SUCCESS when it successfully returns the requested section context. Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |
| STATUS_NOT_SUPPORTED | The volume attached to this instance does not support section contexts. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

**FltGetSectionContext** retrieves a section context that was created for a file stream by a specified minifilter driver instance. A section context is created by calling [**FltCreateSectionForDataScan**](nf-fltkernel-fltcreatesectionfordatascan.md).

**FltGetSectionContext** increments the reference count on the context that the *Context* parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md). Thus every successful call to **FltGetSectionContext** must be matched by a subsequent call to **FltReleaseContext**.

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

Minifilters must not explicitly delete a section context passed to [**FltCreateSectionForDataScan**](nf-fltkernel-fltcreatesectionfordatascan.md). A section context is deallocated and removed from a stream  by calling [**FltCloseSectionForDataScan**](nf-fltkernel-fltclosesectionfordatascan.md) in this case.

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltCloseSectionForDataScan**](nf-fltkernel-fltclosesectionfordatascan.md)

[**FltCreateSectionForDataScan**](nf-fltkernel-fltcreatesectionfordatascan.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)
