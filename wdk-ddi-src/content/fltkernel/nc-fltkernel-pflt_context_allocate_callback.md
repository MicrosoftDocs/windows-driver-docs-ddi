---
UID: NC:fltkernel.PFLT_CONTEXT_ALLOCATE_CALLBACK
title: PFLT_CONTEXT_ALLOCATE_CALLBACK (fltkernel.h)
description: A minifilter driver can register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's ContextAllocateCallback routine.
old-location: ifsk\pflt_context_allocate_callback.htm
tech.root: ifsk
ms.assetid: ca737e84-5b03-4fcd-b715-3344d8bbaaf3
ms.date: 04/16/2018
keywords: ["PFLT_CONTEXT_ALLOCATE_CALLBACK callback function"]
ms.keywords: ContextAllocateCallback, ContextAllocateCallback routine [Installable File System Drivers], FltCallbacks_bbb085f4-6850-424b-9885-01549171458b.xml, PFLT_CONTEXT_ALLOCATE_CALLBACK, fltkernel/ContextAllocateCallback, ifsk.pflt_context_allocate_callback
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFLT_CONTEXT_ALLOCATE_CALLBACK
 - fltkernel/PFLT_CONTEXT_ALLOCATE_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - ContextAllocateCallback
---

# PFLT_CONTEXT_ALLOCATE_CALLBACK callback function


## -description

A minifilter driver can register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's <i>ContextAllocateCallback</i> routine.

## -parameters

### -param PoolType 

[in]
The type of pool to allocate. This parameter is required and must be one of the following: 

<b>NonPagedPool</b>

<b>PagedPool</b>

Must be <b>NonPagedPool</b> if the <i>ContextType</i> parameter is FLT_VOLUME_CONTEXT.

### -param Size 

[in]
The size, in bytes, of the entire context, including both the portion defined by the filter manager and the portion defined by the minifilter driver.

### -param ContextType 

[in]
The type of context. This parameter is required and must be one of the following values: 

FLT_FILE_CONTEXT (starting with Windows Vista)

FLT_INSTANCE_CONTEXT

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_SECTION_CONTEXT (starting with Windows 8)

FLT_TRANSACTION_CONTEXT (starting with  Windows Vista) 

FLT_VOLUME_CONTEXT

## -returns

If not enough free pool is available to satisfy the request, this routine returns a <b>NULL</b> pointer. Otherwise, it returns a pointer to the newly allocated context.

## -remarks

For the rare cases that a minifilter driver must perform its own context allocation, it can specify a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the <i>ContextAllocateCallback</i> routine for each context type that it registers when it calls <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a> from its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. To specify this routine, the minifilter driver stores a pointer to the routine in the <i>ContextAllocateCallback</i> member of the FLT_CONTEXT_REGISTRATION structure for the context type. 

For more information about context registration, see the reference entry for <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_context_cleanup_callback">PFLT_CONTEXT_CLEANUP_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_context_free_callback">PFLT_CONTEXT_FREE_CALLBACK</a>