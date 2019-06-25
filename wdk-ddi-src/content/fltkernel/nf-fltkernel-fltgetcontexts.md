---
UID: NF:fltkernel.FltGetContexts
title: FltGetContexts function (fltkernel.h)
description: The FltGetContexts routine retrieves a minifilter driver's contexts for the objects related to the current operation.
old-location: ifsk\fltgetcontexts.htm
tech.root: ifsk
ms.assetid: 886a0898-814b-4a24-bc83-c6e82e71dae2
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_80c262c0-2587-4ca5-b397-674c0ba5f316.xml, FltGetContexts, FltGetContexts routine [Installable File System Drivers], fltkernel/FltGetContexts, ifsk.fltgetcontexts
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetContexts
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetContexts function


## -description


The <b>FltGetContexts</b> routine retrieves a minifilter driver's contexts for the objects related to the current operation. 


## -parameters




### -param FltObjects [in]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure containing opaque pointers for the objects related to the current operation. (For more information about this parameter, see the  Remarks section.) 


### -param DesiredContexts [in]

Type of contexts to retrieve. This parameter can have one or more of the following values: 

FLT_ALL_CONTEXTS

FLT_FILE_CONTEXT (Windows Vista and later only.)

FLT_INSTANCE_CONTEXT

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_TRANSACTION_CONTEXT (Windows Vista and later only.) 

FLT_VOLUME_CONTEXT


### -param Contexts [out]

Pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a> structure that receives the requested contexts. Contexts that are not requested, or requested but not found, are set to zero. 


## -returns



None 




## -remarks



A minifilter driver calls <b>FltGetContexts</b> to retrieve pointers to the minifilter driver's contexts for the objects in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure. 

The following minifilter driver callback routine types receive a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure as the <i>FltObjects</i> input parameter: 


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_instance_setup_callback">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_instance_query_teardown_callback">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_instance_teardown_callback">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>


<b>FltGetContexts</b> increments the reference count on each of the contexts returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a> structure that the <i>Contexts </i>parameter points to. Thus for every successful call to <b>FltGetContexts</b>, the caller must either: 

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreleasecontexts">FltReleaseContexts</a> for the entire structure that the <i>Contexts </i>parameter points to. 

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> for each of the contexts returned in the structure and set each context field returned in the structure to zero. 

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreleasecontexts">FltReleaseContexts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_instance_query_teardown_callback">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_instance_setup_callback">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_instance_teardown_callback">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

