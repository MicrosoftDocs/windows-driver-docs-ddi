---
UID: NF:fltkernel.FltReferenceContext
title: FltReferenceContext function (fltkernel.h)
description: FltReferenceContext increments the reference count on a context structure.
old-location: ifsk\fltreferencecontext.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltReferenceContext function"]
ms.keywords: FltApiRef_p_to_z_bb2ded16-77d3-4fb3-a6c6-870b0112df7a.xml, FltReferenceContext, FltReferenceContext function [Installable File System Drivers], fltkernel/FltReferenceContext, ifsk.fltreferencecontext
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltReferenceContext
 - fltkernel/FltReferenceContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltReferenceContext
---

# FltReferenceContext function

## -description

**FltReferenceContext** increments the reference count on a context structure.

## -parameters

### -param Context

[in] Pointer to the context. This parameter is required and cannot be **NULL**.

## -returns

None

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

A minifilter driver calls the **FltReferenceContext** routine to increment the reference count on a context structure.

After a successful call to **FltReferenceContext**, the caller is responsible for decrementing the reference count on the context structure by calling [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md).

For more information about context reference counting, see [Referencing Contexts](/windows-hardware/drivers/ifs/referencing-contexts).

To allocate a new context, call [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md).

## -see-also

[**FLT_CONTEXT_REGISTRATION**](ns-fltkernel-_flt_context_registration.md)

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)
