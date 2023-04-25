---
UID: NF:fltkernel.FltGetVolumeContext
title: FltGetVolumeContext function (fltkernel.h)
description: Learn more about the FltGetVolumeContext function.
old-location: ifsk\fltgetvolumecontext.htm
tech.root: ifsk
ms.date: 04/25/2023
keywords: ["FltGetVolumeContext function"]
ms.keywords: FltApiRef_e_to_o_8cec5d5c-18c3-4ffe-be18-fffcfc8d0c14.xml, FltGetVolumeContext, FltGetVolumeContext routine [Installable File System Drivers], fltkernel/FltGetVolumeContext, ifsk.fltgetvolumecontext
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
 - FltGetVolumeContext
 - fltkernel/FltGetVolumeContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetVolumeContext
---

# FltGetVolumeContext function

## -description

The **FltGetVolumeContext** routine retrieves a context that was set for a volume by a given minifilter driver.

## -parameters

### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be NULL.

### -param Volume [in]

Opaque pointer for the volume whose context is being retrieved. This parameter is required and cannot be NULL.

### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the requested context. This parameter is required and can't be set to NULL.

## -returns

**FltGetVolumeContext** returns STATUS_SUCCESS when it successfully returns the requested context. Otherwise, it returns an appropriate NTSTATUS value such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_FOUND | No matching context was found on this file at this time, so *FltMgr* set **Context** to NULL_CONTEXT. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

**FltGetVolumeContext** increments the reference count on the context that the *Context* parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md). Thus every successful call to **FltGetVolumeContext** must be matched by a subsequent call to **FltReleaseContext**.

To set a context for a volume, call [**FltSetVolumeContext**](nf-fltkernel-fltsetvolumecontext.md).

To allocate a new context, call call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To delete a volume context, call [**FltDeleteVolumeContext**](nf-fltkernel-fltdeletevolumecontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteVolumeContext**](nf-fltkernel-fltdeletevolumecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetVolumeContext**](nf-fltkernel-fltsetvolumecontext.md)
