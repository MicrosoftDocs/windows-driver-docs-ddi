---
UID: NC:fltkernel.PFLT_CONTEXT_ALLOCATE_CALLBACK
title: PFLT_CONTEXT_ALLOCATE_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's ContextAllocateCallback routine.
old-location: ifsk\pflt_context_allocate_callback.htm
old-project: ifsk
ms.assetid: ca737e84-5b03-4fcd-b715-3344d8bbaaf3
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
req.alt-api: ContextAllocateCallback
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

# PFLT_CONTEXT_ALLOCATE_CALLBACK callback



## -description
A minifilter driver can register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's <i>ContextAllocateCallback</i> routine. 



## -prototype

````
PFLT_CONTEXT_ALLOCATE_CALLBACK ContextAllocateCallback;

PVOID ContextAllocateCallback(
  _In_ POOL_TYPE        PoolType,
  _In_ SIZE_T           Size,
  _In_ FLT_CONTEXT_TYPE ContextType
)
{ ... }
````


## -parameters

### -param PoolType [in]

The type of pool to allocate. This parameter is required and must be one of the following: 

<dl>
<dd>
<b>NonPagedPool</b>

</dd>
<dd>
<b>PagedPool</b>

</dd>
</dl>
Must be <b>NonPagedPool</b> if the <i>ContextType</i> parameter is FLT_VOLUME_CONTEXT. 


### -param Size [in]

The size, in bytes, of the entire context, including both the portion defined by the filter manager and the portion defined by the minifilter driver. 


### -param ContextType [in]

The type of context. This parameter is required and must be one of the following values: 

<dl>
<dd>
FLT_FILE_CONTEXT (starting with Windows Vista)

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
FLT_SECTION_CONTEXT (starting with Windows 8)

</dd>
<dd>
FLT_TRANSACTION_CONTEXT (starting with  Windows Vista) 

</dd>
<dd>
FLT_VOLUME_CONTEXT

</dd>
</dl>

## -returns
If not enough free pool is available to satisfy the request, this routine returns a <b>NULL</b> pointer. Otherwise, it returns a pointer to the newly allocated context. 


## -remarks
For the rare cases that a minifilter driver must perform its own context allocation, it can specify a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the <i>ContextAllocateCallback</i> routine for each context type that it registers when it calls <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> from its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. To specify this routine, the minifilter driver stores a pointer to the routine in the <i>ContextAllocateCallback</i> member of the FLT_CONTEXT_REGISTRATION structure for the context type. 

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
<a href="..\fltkernel\nc-fltkernel-pflt_context_cleanup_callback.md">PFLT_CONTEXT_CLEANUP_CALLBACK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_context_free_callback.md">PFLT_CONTEXT_FREE_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_CONTEXT_ALLOCATE_CALLBACK routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

