---
UID: NC:fltkernel.PFLT_CONTEXT_CLEANUP_CALLBACK
title: PFLT_CONTEXT_CLEANUP_CALLBACK (fltkernel.h)
description: A minifilter driver can register a routine of type PFLT_CONTEXT_CLEANUP_CALLBACK as the minifilter driver's ContextCleanupCallback routine.
old-location: ifsk\pflt_context_cleanup_callback.htm
tech.root: ifsk
ms.assetid: f17eb108-58d1-4640-a0cc-ae568b0c844c
ms.date: 04/16/2018
keywords: ["PFLT_CONTEXT_CLEANUP_CALLBACK callback function"]
ms.keywords: ContextCleanupCallback, ContextCleanupCallback routine [Installable File System Drivers], FltCallbacks_870edcbe-dbd7-4fad-b4f3-628bffe6fb44.xml, PFLT_CONTEXT_CLEANUP_CALLBACK, fltkernel/ContextCleanupCallback, ifsk.pflt_context_cleanup_callback
f1_keywords:
 - "fltkernel/ContextCleanupCallback"
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- fltkernel.h
api_name:
- ContextCleanupCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFLT_CONTEXT_CLEANUP_CALLBACK callback function


## -description


A minifilter driver can register a routine of type PFLT_CONTEXT_CLEANUP_CALLBACK as the minifilter driver's <i>ContextCleanupCallback</i> routine. 


## -parameters




### -param Context [in]

A pointer to the minifilter driver's portion of the context. 


### -param ContextType [in]

The type of context. Must be one of the following values: 

FLT_FILE_CONTEXT (starting with  Windows Vista)

FLT_INSTANCE_CONTEXT

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_SECTION_CONTEXT (starting with  Windows 8)

FLT_TRANSACTION_CONTEXT (starting with  Windows Vista) 

FLT_VOLUME_CONTEXT


## -remarks



A minifilter driver can optionally specify a routine of type PFLT_CONTEXT_CLEANUP_CALLBACK as the minifilter driver's <i>ContextCleanupCallback</i> routine for each context type that it registers when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. To specify this routine, the minifilter driver stores a pointer to the routine in the <i>ContextCleanupCallback</i> member of the FLT_CONTEXT_REGISTRATION structure for the context type. 

If the minifilter driver specifies a <i>ContextCleanupCallback</i> routine for a context type, the filter manager calls this routine before freeing any of the minifilter driver's contexts of that type. In this routine, the minifilter driver performs any needed cleanup, such as freeing additional memory that the minifilter driver allocated inside the context structure. After the <i>ContextCleanupCallback</i> routine returns, the filter manager frees the context. 

For more information about context registration, see the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_context_allocate_callback">PFLT_CONTEXT_ALLOCATE_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_context_free_callback">PFLT_CONTEXT_FREE_CALLBACK</a>
 

 

