---
UID: NF:fltkernel.FltAllocateContext
title: FltAllocateContext function (fltkernel.h)
description: The FltAllocateContext routine allocates a context structure for a specified context type.
old-location: ifsk\fltallocatecontext.htm
tech.root: ifsk
ms.assetid: 34be4ca1-9484-41c5-9382-4785c36fca1a
ms.date: 04/16/2018
ms.keywords: FltAllocateContext, FltAllocateContext routine [Installable File System Drivers], FltApiRef_a_to_d_dcc03d8c-1f61-4afb-8774-f98951ebfb1f.xml, fltkernel/FltAllocateContext, ifsk.fltallocatecontext
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
- FltAllocateContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltAllocateContext function


## -description


The <b>FltAllocateContext</b> routine allocates a context structure for a specified context type.


## -parameters




### -param Filter [in]

An opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. (Setting this parameter to an invalid value causes the system to execute an ASSERT on a checked build.) 


### -param ContextType [in]

The type of context to allocate. One of the following: 

FLT_FILE_CONTEXT (starting with Windows Vista) 

FLT_INSTANCE_CONTEXT

FLT_SECTION_CONTEXT (starting with Windows 8)

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_TRANSACTION_CONTEXT (starting with Windows Vista) 

FLT_VOLUME_CONTEXT


### -param ContextSize [in]

The size, in bytes, of the portion of the context defined by the minifilter driver. Must be greater than zero and less than or equal to <b>MAXUSHORT</b>. A minifilter driver uses this portion of the context to maintain context information specific to the minifilter driver. The filter manager treats this portion of the context structure as opaque. This parameter is required and cannot be zero. 


### -param PoolType [in]

The type of pool to allocate. This parameter is required and must be one of the following: 

<b>NonPagedPool</b>

<b>PagedPool</b>

Must be <b>NonPagedPool</b> if <i>ContextType</i> is FLT_VOLUME_CONTEXT. 

Setting this parameter to an invalid value causes the system to execute an ASSERT on a checked build. 


### -param ReturnedContext [out]

A pointer to a caller-allocated variable that receives the address of the newly allocated context. The caller is responsible for calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> to release this context when it is no longer needed. 


## -returns



<b>FltAllocateContext</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALLOCATION_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The allocation information for the context of the specified type was not provided at the time of filter registration. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver that is specified in the <i>Filter</i> parameter is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>ContextType</i> or the <i>ContextSize</i> parameter. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The file system does not support per-stream contexts. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltAllocateContext</b> allocates a context of the specified type from the specified pool. The contents of the returned context are not zeroed. 

After the context is allocated, it can be set on an object by passing the <i>ReturnedContext</i> pointer to the appropriate set-context routine from the following table. 

<table>
<tr>
<th>Context Type</th>
<th>Set-Context Routine</th>
</tr>
<tr>
<td>
FLT_FILE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a> (starting with Windows Vista)

</td>
</tr>
<tr>
<td>
FLT_INSTANCE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544521">FltSetInstanceContext</a>


</td>
</tr>
<tr>
<td>
FLT_SECTION_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450937">FltCreateSectionForDataScan</a> (Windows 8 and later only.)

</td>
</tr>
<tr>
<td>
FLT_STREAM_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>


</td>
</tr>
<tr>
<td>
FLT_STREAMHANDLE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>


</td>
</tr>
<tr>
<td>
FLT_TRANSACTION_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a> (starting with Windows Vista)

</td>
</tr>
<tr>
<td>
FLT_VOLUME_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544557">FltSetVolumeContext</a>


</td>
</tr>
</table>
 

When a minifilter driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a> from its <b>DriverEntry</b> routine, it must register each context type that it uses. For more information, see the reference entry for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544629">FLT_CONTEXT_REGISTRATION</a> structure. 

<b>FltAllocateContext</b> does not initialize the contents of the portion of the context structure specific to the minifilter driver. 

To get the context for an object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542997">FltGetContexts</a> or the appropriate get-context routine from the following table.

<table>
<tr>
<th>Context Type</th>
<th>Get-Context Routine</th>
</tr>
<tr>
<td>
FLT_FILE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543025">FltGetFileContext</a> (starting with Windows Vista)

</td>
</tr>
<tr>
<td>
FLT_INSTANCE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543058">FltGetInstanceContext</a>


</td>
</tr>
<tr>
<td>
FLT_SECTION_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450981">FltGetSectionContext</a> (starting with Windows 8)

</td>
</tr>
<tr>
<td>
FLT_STREAM_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543144">FltGetStreamContext</a>


</td>
</tr>
<tr>
<td>
FLT_STREAMHANDLE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>


</td>
</tr>
<tr>
<td>
FLT_TRANSACTION_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a> (starting with Windows Vista )

</td>
</tr>
<tr>
<td>
FLT_VOLUME_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543189">FltGetVolumeContext</a>


</td>
</tr>
</table>
 

Contexts are reference-counted and on a successful return from <b>FltAllocateContext</b>, the context  pointed to by <i>ReturnedContext</i> has a reference count of 1. A context is freed automatically when its reference count reaches zero. To increment the reference count on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544291">FltReferenceContext</a>. 

To decrement the reference count on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. 

Because contexts are reference-counted, it is not usually necessary to delete them. To delete a context explicitly, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a> or the appropriate delete-context routine from the following table.

<table>
<tr>
<th>Context Type</th>
<th>Delete-Context Routine</th>
</tr>
<tr>
<td>
FLT_FILE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541980">FltDeleteFileContext</a> (starting with Windows Vista)

</td>
</tr>
<tr>
<td>
FLT_INSTANCE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541982">FltDeleteInstanceContext</a>


</td>
</tr>
<tr>
<td>
FLT_SECTION_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406456">FltCloseSectionForDataScan</a> (starting with Windows 8)

</td>
</tr>
<tr>
<td>
FLT_STREAM_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a>


</td>
</tr>
<tr>
<td>
FLT_STREAMHANDLE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>


</td>
</tr>
<tr>
<td>
FLT_TRANSACTION_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a> (starting with Windows Vista)

</td>
</tr>
<tr>
<td>
FLT_VOLUME_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542030">FltDeleteVolumeContext</a>


</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544629">FLT_CONTEXT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406456">FltCloseSectionForDataScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450937">FltCreateSectionForDataScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541980">FltDeleteFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541982">FltDeleteInstanceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542030">FltDeleteVolumeContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542997">FltGetContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543025">FltGetFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543058">FltGetInstanceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450981">FltGetSectionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543144">FltGetStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543189">FltGetVolumeContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544291">FltReferenceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544521">FltSetInstanceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544557">FltSetVolumeContext</a>
 

 

