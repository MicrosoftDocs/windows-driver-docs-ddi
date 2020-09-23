---
UID: NF:fltkernel.FltGetContextsEx
title: FltGetContextsEx function (fltkernel.h)
description: The FltGetContextsEx routine retrieves a minifilter driver's contexts for the objects related to the current operation.
old-location: ifsk\fltgetcontextsex.htm
tech.root: ifsk
ms.assetid: 99903B10-5FA8-430F-9E1F-90A45E07B7D0
ms.date: 04/16/2018
keywords: ["FltGetContextsEx function"]
ms.keywords: FltGetContextsEx, FltGetContextsEx routine [Installable File System Drivers], fltkernel/FltGetContextsEx, ifsk.fltgetcontextsex
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
 - FltGetContextsEx
 - fltkernel/FltGetContextsEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetContextsEx
---

# FltGetContextsEx function


## -description

The <b>FltGetContextsEx</b> routine retrieves a minifilter driver's contexts for the objects related to the current operation.

## -parameters

### -param FltObjects 

[in]
Pointer to an <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure containing opaque pointers for the objects related to the current operation. (For more information about this parameter, see the  Remarks section.)

### -param DesiredContexts 

[in]
Type of contexts to retrieve. This parameter can have one or more of the following values: 

FLT_ALL_CONTEXTS

FLT_FILE_CONTEXT (Windows Vista and later only.)

FLT_INSTANCE_CONTEXT

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_TRANSACTION_CONTEXT (Windows Vista and later only.) 

FLT_VOLUME_CONTEXT

FLT_SECTION_CONTEXT (Windows 8 and later only.)

### -param ContextsSize 

[in]
The size, in bytes, of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a> structure pointed to by <i>Contexts</i>. Set to <b>sizeof</b>(FLT_RELATED_CONTEXTS_EX).

### -param Contexts 

[out]
Pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a> structure that receives the requested contexts. Contexts that are not requested, or requested but not found, are set to zero.

## -returns

None

## -remarks

A minifilter driver calls <b>FltGetContextsEx</b> to retrieve pointers to the minifilter driver's contexts for the objects in an <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure. 

The following minifilter driver callback routine types receive a pointer to an <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure as the <i>FltObjects</i> input parameter: 


<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_setup_callback">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_query_teardown_callback">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_teardown_callback">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>


<b>FltGetContextsEx</b> increments the reference count on each of the contexts returned in the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a> structure that the <i>Contexts </i>parameter points to. Thus for every successful call to <b>FltGetContextsEx</b>, the caller must either: 

<ul>
<li>
Call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontextsex">FltReleaseContextsEx</a> for the entire structure that the <i>Contexts</i> parameter points to.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> for each of the contexts returned in the structure and set each context field returned in the structure to zero. 

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts_ex">FLT_RELATED_CONTEXTS_EX</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontextsex">FltReleaseContextsEx</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_query_teardown_callback">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_setup_callback">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_teardown_callback">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>