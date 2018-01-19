---
UID: NC:fltkernel.PFLT_CONTEXT_CLEANUP_CALLBACK
title: PFLT_CONTEXT_CLEANUP_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_CONTEXT_CLEANUP_CALLBACK as the minifilter driver's ContextCleanupCallback routine.
old-location: ifsk\pflt_context_cleanup_callback.htm
old-project: ifsk
ms.assetid: f17eb108-58d1-4640-a0cc-ae568b0c844c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
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
req.alt-api: ContextCleanupCallback
req.alt-loc: fltkernel.h
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
req.typenames: EXpsFontRestriction
---

# PFLT_CONTEXT_CLEANUP_CALLBACK callback



## -description
A minifilter driver can register a routine of type PFLT_CONTEXT_CLEANUP_CALLBACK as the minifilter driver's <i>ContextCleanupCallback</i> routine. 



## -prototype

````
PFLT_CONTEXT_CLEANUP_CALLBACK ContextCleanupCallback;

VOID ContextCleanupCallback(
  _In_ PFLT_CONTEXT     Context,
  _In_ FLT_CONTEXT_TYPE ContextType
)
{ ... }
````


## -parameters

### -param Context [in]

A pointer to the minifilter driver's portion of the context. 


### -param ContextType [in]

The type of context. Must be one of the following values: 

<dl>
<dd>
FLT_FILE_CONTEXT (starting with  Windows Vista)

</dd>
<dd>
FLT_INSTANCE_CONTEXT

</dd>
<dd>
FLT_STREAM_CONTEXT

</dd>
<dd>
FLT_STREAMHANDLE_CONTEXT

</dd>
<dd>
FLT_SECTION_CONTEXT (starting with  Windows 8)

</dd>
<dd>
FLT_TRANSACTION_CONTEXT (starting with  Windows Vista) 

</dd>
<dd>
FLT_VOLUME_CONTEXT

</dd>
</dl>

## -returns
None. 


## -remarks
A minifilter driver can optionally specify a routine of type PFLT_CONTEXT_CLEANUP_CALLBACK as the minifilter driver's <i>ContextCleanupCallback</i> routine for each context type that it registers when it calls <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> from its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. To specify this routine, the minifilter driver stores a pointer to the routine in the <i>ContextCleanupCallback</i> member of the FLT_CONTEXT_REGISTRATION structure for the context type. 

If the minifilter driver specifies a <i>ContextCleanupCallback</i> routine for a context type, the filter manager calls this routine before freeing any of the minifilter driver's contexts of that type. In this routine, the minifilter driver performs any needed cleanup, such as freeing additional memory that the minifilter driver allocated inside the context structure. After the <i>ContextCleanupCallback</i> routine returns, the filter manager frees the context. 

For more information about context registration, see the reference entry for <a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>
</dt>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_context_allocate_callback.md">PFLT_CONTEXT_ALLOCATE_CALLBACK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_context_free_callback.md">PFLT_CONTEXT_FREE_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_CONTEXT_CLEANUP_CALLBACK routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

