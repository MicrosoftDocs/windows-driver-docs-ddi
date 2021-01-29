---
UID: NF:fltkernel.FltSetVolumeContext
title: FltSetVolumeContext function (fltkernel.h)
description: FltSetVolumeContext sets a context for a volume.
old-location: ifsk\fltsetvolumecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltSetVolumeContext function"]
ms.keywords: FltApiRef_p_to_z_889de924-a441-479f-9818-da016dd3feb3.xml, FltSetVolumeContext, FltSetVolumeContext function [Installable File System Drivers], fltkernel/FltSetVolumeContext, ifsk.fltsetvolumecontext
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
 - FltSetVolumeContext
 - fltkernel/FltSetVolumeContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSetVolumeContext
---

# FltSetVolumeContext function

## -description

**FltSetVolumeContext** sets a context for a volume.

## -parameters

### -param Volume

[in] Opaque volume pointer for the volume.

### -param Operation

[in] Flag specifying details of the operation to be performed. This parameter must be one of the following:

| Flag | Meaning |
| ---- | ------- |
| FLT_SET_CONTEXT_REPLACE_IF_EXISTS | If a context is already set for *Volume*, **FltSetVolumeContext** will replace it with *NewContext*>. Otherwise, it will insert *NewContext* into the list of contexts for the volume. |
| FLT_SET_CONTEXT_KEEP_IF_EXISTS | If a context is already set for this volume, **FltSetVolumeContext** will return STATUS_FLT_CONTEXT_ALREADY_DEFINED, and will not replace the existing context or increment the reference count. If a context has not already been set, the routine will insert *NewContext* into the list of contexts for the volume and increment the reference count. |

### -param NewContext

[in] Pointer to the new context to be set for the volume. This parameter is required and cannot be **NULL**.

### -param OldContext

[out, optional] Pointer to a caller-allocated variable that receives the address of the existing volume context for *Volume*. This parameter is optional and can be **NULL**. For more information about this parameter, see the following Remarks section.

## -returns

**FltSetVolumeContext** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_CONTEXT_ALREADY_DEFINED | IF FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for *Operation*, this error code indicates that a context is already attached to the volume. |
| STATUS_FLT_CONTEXT_ALREADY_LINKED | The context pointed to by the *NewContext* parameter is already linked to an object.  In other words, this error code indicates that *NewContext* is already in use due to a successful prior call of a **FltSet***Xxx***Context** routine. |
| STATUS_FLT_DELETING_OBJECT | The specified *Volume* is being torn down. This is an error code. |
| STATUS_INVALID_PARAMETER | An invalid parameter was passed. For example, the *NewContext* parameter does not point to a valid volume context, or an invalid value was specified for *Operation*. This is an error code. |

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

A minifilter driver calls **FltSetVolumeContext** to attach a context to a volume, or to remove or replace an existing volume context. A minifilter driver can attach only one context to a volume.

### Reference Counting

If **FltSetVolumeContext** succeeds:

- The reference count on *NewContext* is incremented. When *NewContext* is no longer needed, the minifilter must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to decrement its reference count.

Else if **FltSetVolumeContext** fails:

- The reference count on *NewContext* remains unchanged.
- If *OldContext* is not **NULL** and does not point to NULL_CONTEXT then *OldContext* is a referenced pointer to the context currently associated with the volume. The filter calling **FltSetVolumeContext** must call **FltReleaseContext** for *OldContext* as well when the context pointer is no longer needed.

Regardless of success:

- The filter calling **FltSetVolumeContext** must call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) to decrement the reference count on the *NewContext* object that was incremented by [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

For more information, see [Referencing Contexts](/windows-hardware/drivers/ifs/referencing-contexts).

### Other context operations

For more information, see [Setting Contexts](/windows-hardware/drivers/ifs/setting-contexts), and [Releasing Contexts](/windows-hardware/drivers/ifs/releasing-contexts):

- To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

- To get a volume context, call [**FltGetVolumeContext**](nf-fltkernel-fltgetvolumecontext.md).

- To delete a volume context, call [**FltDeleteVolumeContext**](nf-fltkernel-fltdeletevolumecontext.md) or [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md).

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteVolumeContext**](nf-fltkernel-fltdeletevolumecontext.md)

[**FltGetVolumeContext**](nf-fltkernel-fltgetvolumecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)
