---
UID: NF:fltkernel.FltGetInstanceContext
title: FltGetInstanceContext function (fltkernel.h)
description: Learn more about the FltGetInstanceContext function.
old-location: ifsk\fltgetinstancecontext.htm
tech.root: ifsk
ms.date: 04/25/2023
keywords: ["FltGetInstanceContext function"]
ms.keywords: FltApiRef_e_to_o_8d05bb2a-ad52-454b-89d6-b15413c34e7f.xml, FltGetInstanceContext, FltGetInstanceContext routine [Installable File System Drivers], fltkernel/FltGetInstanceContext, ifsk.fltgetinstancecontext
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
 - FltGetInstanceContext
 - fltkernel/FltGetInstanceContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetInstanceContext
---

# FltGetInstanceContext function

## -description

The **FltGetInstanceContext** routine retrieves a context that was set for an instance by a given minifilter driver.

## -parameters

### -param Instance [in]

Opaque instance pointer for the instance.

### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the instance context. This parameter is required and can't be set to NULL.

## -returns

**FltGetInstanceContext** returns STATUS_SUCCESS when it successfully returns the requested instance context. Otherwise, it returns an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_FOUND | No matching context was found on this instance at this time. *FltMgr* sets **Context** to NULL_CONTEXT. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

**FltGetInstanceContext** retrieves a context that was set for an instance by a given minifilter driver.

**FltGetInstanceContext** increments the reference count on the context that the *Context* parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md). Thus every successful call to **FltGetInstanceContext** must be matched by a subsequent call to **FltReleaseContext**.

To set a context for an instance, call [**FltSetInstanceContext**](nf-fltkernel-fltsetinstancecontext.md).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To delete a file context, call [**FltDeleteInstanceContext**](nf-fltkernel-fltdeleteinstancecontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteInstanceContext**](nf-fltkernel-fltdeleteinstancecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetInstanceContext**](nf-fltkernel-fltsetinstancecontext.md)
