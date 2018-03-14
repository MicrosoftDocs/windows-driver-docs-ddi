---
UID: NC:fltkernel.PFLT_NORMALIZE_CONTEXT_CLEANUP
title: PFLT_NORMALIZE_CONTEXT_CLEANUP
author: windows-driver-content
description: A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP as the minifilter driver's NormalizeContextCleanupCallback routine.
old-location: ifsk\pflt_normalize_context_cleanup.htm
old-project: ifsk
ms.assetid: 968cfc99-4862-41f7-bf7e-d579a3e8061f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltCallbacks_3391a3bd-55a2-4f87-b116-78c2e4f93b88.xml, NormalizeContextCleanupCallback, NormalizeContextCleanupCallback routine [Installable File System Drivers], PFLT_NORMALIZE_CONTEXT_CLEANUP, fltkernel/NormalizeContextCleanupCallback, ifsk.pflt_normalize_context_cleanup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fltkernel.h
api_name:
-	NormalizeContextCleanupCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_NORMALIZE_CONTEXT_CLEANUP callback


## -description


A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP as the minifilter driver's <i>NormalizeContextCleanupCallback</i> routine. 


## -prototype


````
PFLT_NORMALIZE_CONTEXT_CLEANUP NormalizeContextCleanupCallback;

VOID NormalizeContextCleanupCallback(
  _In_opt_ PVOID *NormalizationContext
)
{ ... }
````


## -parameters




### -param *NormalizationContext [in, optional]

Pointer to minifilter driver-provided context information to be passed in any calls to the <a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md">PFLT_NORMALIZE_NAME_COMPONENT</a> callback routine that are made to normalize multiple components in the same file name path. 


## -returns



None. 




## -remarks



A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP as the minifilter driver's <i>NormalizeContextCleanupCallback</i> routine. 

To register this callback routine, the minifilter driver stores the address of a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP in the <b>NormalizeContextCleanupCallback</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> structure that the minifilter driver passes as a parameter to <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 

The filter manager calls this callback routine to allow the minifilter driver to perform any needed cleanup for the context information passed in the <i>NormalizationContext</i> parameter of the <a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md">PFLT_NORMALIZE_NAME_COMPONENT</a> callback routine. This context is set by the minifilter driver when its PFLT_NORMALIZE_NAME_COMPONENT callback routine is called. 




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md">PFLT_NORMALIZE_NAME_COMPONENT</a>



<a href="..\fltkernel\nc-fltkernel-pflt_generate_file_name.md">PFLT_GENERATE_FILE_NAME</a>



<a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component_ex.md">PFLT_NORMALIZE_NAME_COMPONENT_EX</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_NORMALIZE_CONTEXT_CLEANUP routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

