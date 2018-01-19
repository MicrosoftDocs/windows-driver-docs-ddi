---
UID: NF:fltkernel.FltAllocateContext
title: FltAllocateContext function
author: windows-driver-content
description: The FltAllocateContext routine allocates a context structure for a specified context type.
old-location: ifsk\fltallocatecontext.htm
old-project: ifsk
ms.assetid: 34be4ca1-9484-41c5-9382-4785c36fca1a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltAllocateContext
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
req.alt-api: FltAllocateContext
req.alt-loc: fltmgr.sys
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
req.typenames: EXpsFontRestriction
---

# FltAllocateContext function



## -description
The <b>FltAllocateContext</b> routine allocates a context structure for a specified context type.



## -syntax

````
NTSTATUS FltAllocateContext(
  _In_  PFLT_FILTER      Filter,
  _In_  FLT_CONTEXT_TYPE ContextType,
  _In_  SIZE_T           ContextSize,
  _In_  POOL_TYPE        PoolType,
  _Out_ PFLT_CONTEXT     *ReturnedContext
);
````


## -parameters

### -param Filter [in]

An opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. (Setting this parameter to an invalid value causes the system to execute an ASSERT on a checked build.) 


### -param ContextType [in]

The type of context to allocate. One of the following: 

<dl>
<dd>
FLT_FILE_CONTEXT (starting with Windows Vista) 

</dd>
<dd>
FLT_INSTANCE_CONTEXT

</dd>
<dd>
FLT_SECTION_CONTEXT (starting with Windows 8)

</dd>
<dd>
FLT_STREAM_CONTEXT

</dd>
<dd>
FLT_STREAMHANDLE_CONTEXT

</dd>
<dd>
FLT_TRANSACTION_CONTEXT (starting with Windows Vista) 

</dd>
<dd>
FLT_VOLUME_CONTEXT

</dd>
</dl>

### -param ContextSize [in]

The size, in bytes, of the portion of the context defined by the minifilter driver. Must be greater than zero and less than or equal to <b>MAXUSHORT</b>. A minifilter driver uses this portion of the context to maintain context information specific to the minifilter driver. The filter manager treats this portion of the context structure as opaque. This parameter is required and cannot be zero. 


### -param PoolType [in]

The type of pool to allocate. This parameter is required and must be one of the following: 

<b>NonPagedPool</b>

<b>PagedPool</b>

Must be <b>NonPagedPool</b> if <i>ContextType</i> is FLT_VOLUME_CONTEXT. 

Setting this parameter to an invalid value causes the system to execute an ASSERT on a checked build. 


### -param ReturnedContext [out]

A pointer to a caller-allocated variable that receives the address of the newly allocated context. The caller is responsible for calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> to release this context when it is no longer needed. 


## -returns
<b>FltAllocateContext</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following. 
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALLOCATION_NOT_FOUND</b></dt>
</dl>The allocation information for the context of the specified type was not provided at the time of filter registration. This is an error code.
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The minifilter driver that is specified in the <i>Filter</i> parameter is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a> encountered a pool allocation failure. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid value was specified for the <i>ContextType</i> or the <i>ContextSize</i> parameter. This is an error code. 
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The file system does not support per-stream contexts. This is an error code. 

 


## -remarks
<b>FltAllocateContext</b> allocates a context of the specified type from the specified pool. The contents of the returned context are not zeroed. 

After the context is allocated, it can be set on an object by passing the <i>ReturnedContext</i> pointer to the appropriate set-context routine from the following table. 

FLT_FILE_CONTEXT


<a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a> (starting with Windows Vista)

FLT_INSTANCE_CONTEXT


<a href="..\fltkernel\nf-fltkernel-fltsetinstancecontext.md">FltSetInstanceContext</a>


FLT_SECTION_CONTEXT


<a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a> (Windows 8 and later only.)

FLT_STREAM_CONTEXT


<a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>


FLT_STREAMHANDLE_CONTEXT


<a href="..\fltkernel\nf-fltkernel-fltsetstreamhandlecontext.md">FltSetStreamHandleContext</a>


FLT_TRANSACTION_CONTEXT


<a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a> (starting with Windows Vista)

FLT_VOLUME_CONTEXT


<a href="..\fltkernel\nf-fltkernel-fltsetvolumecontext.md">FltSetVolumeContext</a>


When a minifilter driver calls <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> from its <b>DriverEntry</b> routine, it must register each context type that it uses. For more information, see the reference entry for the <a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a> structure. 

<b>FltAllocateContext</b> does not initialize the contents of the portion of the context structure specific to the minifilter driver. 

To get the context for an object, call <a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a> or the appropriate get-context routine from the following table.


<a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a> (starting with Windows Vista)


<a href="..\fltkernel\nf-fltkernel-fltgetinstancecontext.md">FltGetInstanceContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetsectioncontext.md">FltGetSectionContext</a> (starting with Windows 8)


<a href="..\fltkernel\nf-fltkernel-fltgetstreamcontext.md">FltGetStreamContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetstreamhandlecontext.md">FltGetStreamHandleContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgettransactioncontext.md">FltGetTransactionContext</a> (starting with Windows Vista )


<a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>


Contexts are reference-counted and on a successful return from <b>FltAllocateContext</b>, the context  pointed to by <i>ReturnedContext</i> has a reference count of 1. A context is freed automatically when its reference count reaches zero. To increment the reference count on a context, call <a href="..\fltkernel\nf-fltkernel-fltreferencecontext.md">FltReferenceContext</a>. 

To decrement the reference count on a context, call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. 

Because contexts are reference-counted, it is not usually necessary to delete them. To delete a context explicitly, call <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a> or the appropriate delete-context routine from the following table.


<a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a> (starting with Windows Vista)


<a href="..\fltkernel\nf-fltkernel-fltdeleteinstancecontext.md">FltDeleteInstanceContext</a>



<a href="..\fltkernel\nf-fltkernel-fltclosesectionfordatascan.md">FltCloseSectionForDataScan</a> (starting with Windows 8)


<a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletestreamhandlecontext.md">FltDeleteStreamHandleContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a> (starting with Windows Vista)


<a href="..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md">FltDeleteVolumeContext</a>



## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltclosesectionfordatascan.md">FltCloseSectionForDataScan</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeleteinstancecontext.md">FltDeleteInstanceContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletestreamhandlecontext.md">FltDeleteStreamHandleContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md">FltDeleteTransactionContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md">FltDeleteVolumeContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetinstancecontext.md">FltGetInstanceContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetsectioncontext.md">FltGetSectionContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetstreamcontext.md">FltGetStreamContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetstreamhandlecontext.md">FltGetStreamHandleContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgettransactioncontext.md">FltGetTransactionContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreferencecontext.md">FltReferenceContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetinstancecontext.md">FltSetInstanceContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetstreamhandlecontext.md">FltSetStreamHandleContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsettransactioncontext.md">FltSetTransactionContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetvolumecontext.md">FltSetVolumeContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAllocateContext routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

