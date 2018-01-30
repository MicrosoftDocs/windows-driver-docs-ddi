---
UID: NC:fltkernel.PFLT_CONTEXT_FREE_CALLBACK
title: PFLT_CONTEXT_FREE_CALLBACK
author: windows-driver-content
description: A minifilter can register a routine of type PFLT_CONTEXT_FREE_CALLBACK as the minifilter driver's ContextFreeCallback routine.
old-location: ifsk\pflt_context_free_callback.htm
old-project: ifsk
ms.assetid: 11c397c2-51a5-4acd-8029-cd002f990366
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.pflt_context_free_callback, ContextFreeCallback routine [Installable File System Drivers], ContextFreeCallback, PFLT_CONTEXT_FREE_CALLBACK, PFLT_CONTEXT_FREE_CALLBACK, fltkernel/ContextFreeCallback, FltCallbacks_c7e2b5e1-5666-431c-9032-59914ef23336.xml
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
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	fltkernel.h
apiname:
-	ContextFreeCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_CONTEXT_FREE_CALLBACK callback


## -description


A minifilter can register a routine of type PFLT_CONTEXT_FREE_CALLBACK as the minifilter driver's <i>ContextFreeCallback</i> routine. 


## -prototype


````
PFLT_CONTEXT_FREE_CALLBACK ContextFreeCallback;

VOID ContextFreeCallback(
  _In_ PVOID            Pool,
  _In_ FLT_CONTEXT_TYPE ContextType
)
{ ... }
````


## -parameters




### -param Pool [in]

A pointer to the context to be freed. 


### -param ContextType [in]

The type of context. This parameter is required and must be one of the following values: 

FLT_FILE_CONTEXT (starting with  Windows Vista)

FLT_INSTANCE_CONTEXT

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_SECTION_CONTEXT (starting with Windows 8)

FLT_TRANSACTION_CONTEXT (starting with  Windows Vista) 

FLT_VOLUME_CONTEXT


## -returns


None. 



## -remarks


For the rare cases that a minifilter driver must free its own contexts manually, the minifilter driver can specify a routine of type PFLT_CONTEXT_FREE_CALLBACK as the minifilter driver's <i>ContextFreeCallback</i> routine for each context type that it registers when it calls <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> from its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. To specify this routine, the minifilter driver stores a pointer to the routine in the <i>ContextFreeCallback</i> member of the FLT_CONTEXT_REGISTRATION structure for the context type. 

For more information about context registration, see the reference entry for <a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>. 



## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>

<a href="..\fltkernel\nc-fltkernel-pflt_context_cleanup_callback.md">PFLT_CONTEXT_CLEANUP_CALLBACK</a>

<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>

<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>

<a href="..\fltkernel\nc-fltkernel-pflt_context_allocate_callback.md">PFLT_CONTEXT_ALLOCATE_CALLBACK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_CONTEXT_FREE_CALLBACK routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

