---
UID: NF:fltkernel.FltGetContexts
title: FltGetContexts function (fltkernel.h)
description: Learn more about the FltGetContexts function.
old-location: ifsk\fltgetcontexts.htm
tech.root: ifsk
ms.date: 04/25/2023
keywords: ["FltGetContexts function"]
ms.keywords: FltApiRef_e_to_o_80c262c0-2587-4ca5-b397-674c0ba5f316.xml, FltGetContexts, FltGetContexts routine [Installable File System Drivers], fltkernel/FltGetContexts, ifsk.fltgetcontexts
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
 - FltGetContexts
 - fltkernel/FltGetContexts
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetContexts
---

# FltGetContexts function

## -description

The **FltGetContexts** routine retrieves a minifilter driver's contexts for the objects related to the current operation.

## -parameters

### -param FltObjects

[in] Pointer to a [**FLT_RELATED_OBJECTS**](ns-fltkernel-_flt_related_objects.md) structure containing opaque pointers for the objects related to the current operation. For more information about this parameter, see the Remarks section.

### -param DesiredContexts

[in] Identifies the types of contexts to retrieve. This parameter can be a bitwise OR of the following values.

| Constant | Value |
| -------- | ----- |
| FLT_VOLUME_CONTEXT                              | 0x0001 |
| FLT_INSTANCE_CONTEXT                            | 0x0002 |
| FLT_FILE_CONTEXT                                | 0x0004 |
| FLT_STREAM_CONTEXT                              | 0x0008 |
| FLT_STREAMHANDLE_CONTEXT                        | 0x0010 |
| FLT_TRANSACTION_CONTEXT                         | 0x0020 |
| FLT_SECTION_CONTEXT (starting in Windows 8)     | 020040 |
| FLT_ALL_CONTEXTS                                | Bitwise OR of all of the context values |

### -param Contexts

[out] Pointer to a caller-allocated [**FLT_RELATED_CONTEXTS**](ns-fltkernel-_flt_related_contexts.md) structure that receives the requested contexts. This parameter is required and cannot be set to NULL. *FltMgr* sets a structure member to zero for:

* Contexts that the caller did not request.
* Contexts that the caller requested but *FltMgr* couldn't find.

## -remarks

For more information about contexts, see [About minifilter contexts](/windows-hardware/drivers/ifs/managing-contexts-in-a-minifilter-driver).

A minifilter driver calls **FltGetContexts** to retrieve pointers to the minifilter driver's contexts for the objects in a [**FLT_RELATED_OBJECTS**](ns-fltkernel-_flt_related_objects.md) structure.

The following minifilter driver callback routine types receive a pointer to a [**FLT_RELATED_OBJECTS**](ns-fltkernel-_flt_related_objects.md) structure as the **FltObjects** input parameter:

* [**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)
* [**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)
* [**PFLT_INSTANCE_SETUP_CALLBACK**](nc-fltkernel-pflt_instance_setup_callback.md)
* [**PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK**](nc-fltkernel-pflt_instance_query_teardown_callback.md)
* [**PFLT_INSTANCE_TEARDOWN_CALLBACK**](nc-fltkernel-pflt_instance_teardown_callback.md)

**FltGetContexts** increments the reference count on each of the contexts returned in the [**FLT_RELATED_CONTEXTS**](ns-fltkernel-_flt_related_contexts.md) structure that the **Contexts** parameter points to. Thus for every successful call to **FltGetContexts**, the caller must either:

* Call [**FltReleaseContexts**](nf-fltkernel-fltreleasecontexts.md) for the entire structure that the *Contexts* parameter points to.
* Call [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md) for each of the contexts returned in the structure and set each context field returned in the structure to zero.

## -see-also

[**FLT_RELATED_CONTEXTS**](ns-fltkernel-_flt_related_contexts.md)

[**FLT_RELATED_OBJECTS**](ns-fltkernel-_flt_related_objects.md)

[**FltGetContextsEx**](nf-fltkernel-fltgetcontextsex.md)

[**FltRegisterFilter**](nf-fltkernel-fltregisterfilter.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltReleaseContexts**](nf-fltkernel-fltreleasecontexts.md)

[**PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK**](nc-fltkernel-pflt_instance_query_teardown_callback.md)

[**PFLT_INSTANCE_SETUP_CALLBACK**](nc-fltkernel-pflt_instance_setup_callback.md)

[**PFLT_INSTANCE_TEARDOWN_CALLBACK**](nc-fltkernel-pflt_instance_teardown_callback.md)

[**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)

[**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)
