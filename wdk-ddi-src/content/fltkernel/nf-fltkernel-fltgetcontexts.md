---
UID: NF:fltkernel.FltGetContexts
title: FltGetContexts function
author: windows-driver-content
description: The FltGetContexts routine retrieves a minifilter driver's contexts for the objects related to the current operation.
old-location: ifsk\fltgetcontexts.htm
old-project: ifsk
ms.assetid: 886a0898-814b-4a24-bc83-c6e82e71dae2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_80c262c0-2587-4ca5-b397-674c0ba5f316.xml, FltGetContexts, FltGetContexts routine [Installable File System Drivers], fltkernel/FltGetContexts, ifsk.fltgetcontexts
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetContexts
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetContexts function


## -description


The <b>FltGetContexts</b> routine retrieves a minifilter driver's contexts for the objects related to the current operation. 


## -syntax


````
VOID FltGetContexts(
  _In_  PCFLT_RELATED_OBJECTS FltObjects,
  _In_  FLT_CONTEXT_TYPE      DesiredContexts,
  _Out_ PFLT_RELATED_CONTEXTS Contexts
);
````


## -parameters




### -param FltObjects [in]

Pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure containing opaque pointers for the objects related to the current operation. (For more information about this parameter, see the  Remarks section.) 


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

Pointer to a caller-allocated <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts.md">FLT_RELATED_CONTEXTS</a> structure that receives the requested contexts. Contexts that are not requested, or requested but not found, are set to zero. 


## -returns



None 




## -remarks



A minifilter driver calls <b>FltGetContexts</b> to retrieve pointers to the minifilter driver's contexts for the objects in an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure. 

The following minifilter driver callback routine types receive a pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure as the <i>FltObjects</i> input parameter: 


<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_query_teardown_callback.md">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>


<b>FltGetContexts</b> increments the reference count on each of the contexts returned in the <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts.md">FLT_RELATED_CONTEXTS</a> structure that the <i>Contexts </i>parameter points to. Thus for every successful call to <b>FltGetContexts</b>, the caller must either: 

<ul>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltreleasecontexts.md">FltReleaseContexts</a> for the entire structure that the <i>Contexts </i>parameter points to. 

</li>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> for each of the contexts returned in the structure and set each context field returned in the structure to zero. 

</li>
</ul>



## -see-also

<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_query_teardown_callback.md">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>



<a href="..\fltkernel\ns-fltkernel-_flt_related_contexts.md">FLT_RELATED_CONTEXTS</a>



<a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a>



<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontexts.md">FltReleaseContexts</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetContexts routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

