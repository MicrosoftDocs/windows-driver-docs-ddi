---
UID: NF:fltkernel.FltGetContextsEx
title: FltGetContextsEx function
author: windows-driver-content
description: The FltGetContextsEx routine retrieves a minifilter driver's contexts for the objects related to the current operation.
old-location: ifsk\fltgetcontextsex.htm
old-project: ifsk
ms.assetid: 99903B10-5FA8-430F-9E1F-90A45E07B7D0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltGetContextsEx routine [Installable File System Drivers], fltkernel/FltGetContextsEx, ifsk.fltgetcontextsex, FltGetContextsEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltGetContextsEx
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetContextsEx function


## -description


The <b>FltGetContextsEx</b> routine retrieves a minifilter driver's contexts for the objects related to the current operation. 


## -syntax


````
VOID FltGetContextsEx(
  _In_  PCFLT_RELATED_OBJECTS    FltObjects,
  _In_  FLT_CONTEXT_TYPE         DesiredContexts,
  _In_  SIZE_T                   ContextsSize,
  _Out_ PFLT_RELATED_CONTEXTS_EX Contexts
);
````


## -parameters




### -param FltObjects [in]

Pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure containing opaque pointers for the objects related to the current operation. (For more information about this parameter, see the  Remarks section.) 


### -param DesiredContexts [in]

Type of contexts to retrieve. This parameter can have one or more of the following values: 

FLT_ALL_CONTEXTS

FLT_FILE_CONTEXT (Windows Vista and later only.)

FLT_INSTANCE_CONTEXT

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_TRANSACTION_CONTEXT (Windows Vista and later only.) 

FLT_VOLUME_CONTEXT

FLT_SECTION_CONTEXT (Windows 8 and later only.)


### -param ContextsSize [in]

The size, in bytes, of the <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts_ex.md">FLT_RELATED_CONTEXTS_EX</a> structure pointed to by <i>Contexts</i>. Set to <b>sizeof</b>(FLT_RELATED_CONTEXTS_EX).


### -param Contexts [out]

Pointer to a caller-allocated <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts_ex.md">FLT_RELATED_CONTEXTS_EX</a> structure that receives the requested contexts. Contexts that are not requested, or requested but not found, are set to zero. 


## -returns



None 




## -remarks



A minifilter driver calls <b>FltGetContextsEx</b> to retrieve pointers to the minifilter driver's contexts for the objects in an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure. 

The following minifilter driver callback routine types receive a pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure as the <i>FltObjects</i> input parameter: 


<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_query_teardown_callback.md">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>


<b>FltGetContextsEx</b> increments the reference count on each of the contexts returned in the <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts_ex.md">FLT_RELATED_CONTEXTS_EX</a> structure that the <i>Contexts </i>parameter points to. Thus for every successful call to <b>FltGetContextsEx</b>, the caller must either: 

<ul>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltreleasecontextsex.md">FltReleaseContextsEx</a> for the entire structure that the <i>Contexts</i> parameter points to.

</li>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> for each of the contexts returned in the structure and set each context field returned in the structure to zero. 

</li>
</ul>



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



<a href="..\fltkernel\ns-fltkernel-_flt_related_contexts_ex.md">FLT_RELATED_CONTEXTS_EX</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontextsex.md">FltReleaseContextsEx</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_query_teardown_callback.md">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetContextsEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

