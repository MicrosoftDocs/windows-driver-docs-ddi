---
UID: NF:fltkernel.FltDeleteVolumeContext
title: FltDeleteVolumeContext function (fltkernel.h)
description: FltDeleteVolumeContext removes a context that a given minifilter driver has set for a given volume and marks the context for deletion.
old-location: ifsk\fltdeletevolumecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltDeleteVolumeContext function"]
ms.keywords: FltApiRef_a_to_d_261f2efb-7c2e-4f85-a75c-b5cf55236271.xml, FltDeleteVolumeContext, FltDeleteVolumeContext function [Installable File System Drivers], fltkernel/FltDeleteVolumeContext, ifsk.fltdeletevolumecontext
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
 - FltDeleteVolumeContext
 - fltkernel/FltDeleteVolumeContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDeleteVolumeContext
---

# FltDeleteVolumeContext function

## -description

**FltDeleteVolumeContext** removes a context that a given minifilter driver has set for a given volume and marks the context for deletion.

## -parameters

### -param Filter

[in] Opaque filter pointer for the caller.

### -param Volume

[in] Opaque volume pointer for the volume.

### -param OldContext

[out, optional] Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be **NULL**. If *OldContext* is not **NULL** and does not point to NULL_CONTEXT, the caller is responsible for calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to release this context when it is no longer needed.

## -returns

**FltDeleteVolumeContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The specified *Volume* is being torn down. This is an error code. |
| STATUS_NOT_FOUND | No matching context was found. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as **FltDeleteVolumeContext** to explicitly delete a context.

A minifilter driver calls **FltDeleteVolumeContext** to remove a context from a volume and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still in use by another thread).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

To get a volume context, call [**FltGetVolumeContext**](nf-fltkernel-fltgetvolumecontext.md).

To set a volume context, call [**FltSetVolumeContext**](nf-fltkernel-fltsetvolumecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltGetVolumeContext**](nf-fltkernel-fltgetvolumecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetVolumeContext**](nf-fltkernel-fltsetvolumecontext.md)
