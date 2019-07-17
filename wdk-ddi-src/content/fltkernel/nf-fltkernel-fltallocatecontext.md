---
UID: NF:fltkernel.FltAllocateContext
title: FltAllocateContext function (fltkernel.h)
description: The FltAllocateContext routine allocates a context structure for a specified context type.
old-location: ifsk\fltallocatecontext.htm
tech.root: ifsk
ms.assetid: 34be4ca1-9484-41c5-9382-4785c36fca1a
ms.date: 05/29/2019
ms.keywords: FltAllocateContext, FltAllocateContext routine [Installable File System Drivers], FltApiRef_a_to_d_dcc03d8c-1f61-4afb-8774-f98951ebfb1f.xml, fltkernel/FltAllocateContext, ifsk.fltallocatecontext
ms.topic: function
f1_keywords:
 - "fltkernel/FltAllocateContext"
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
req.irql: <= APC_LEVEL
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

The **FltAllocateContext** routine allocates a context structure for a specified context type.

## -parameters

### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be **NULL**. (Setting this parameter to an invalid value causes the system to execute an ASSERT on a checked build.)

### -param ContextType [in]

The type of context to allocate. *ContextType* can be one of the following:

* FLT_FILE_CONTEXT (starting with Windows Vista)
* FLT_INSTANCE_CONTEXT
* FLT_SECTION_CONTEXT (starting with Windows 8)
* FLT_STREAM_CONTEXT
* FLT_STREAMHANDLE_CONTEXT
* FLT_TRANSACTION_CONTEXT (starting with Windows Vista)
* FLT_VOLUME_CONTEXT

### -param ContextSize [in]

The size, in bytes, of the portion of the context defined by the minifilter driver. Must be greater than zero and less than or equal to **MAXUSHORT**; for fixed-size contexts, must be less than or equal to the *Size* specified in the [FLT_CONTEXT_REGISTRATION](ns-fltkernel-_flt_context_registration.md) structure. A minifilter driver uses this portion of the context to maintain context information specific to the minifilter driver. The filter manager treats this portion of the context structure as opaque. This parameter is required and cannot be zero.

### -param PoolType [in]

The type of pool to allocate. This parameter is required and must be one of the following:

* **NonPagedPool**
* **PagedPool** (must be **NonPagedPool** if *ContextType* is FLT_VOLUME_CONTEXT)

Setting this parameter to an invalid value causes the system to execute an ASSERT on a checked build.

### -param ReturnedContext [out]

Pointer to a caller-allocated variable that receives the address of the newly allocated context. The caller is responsible for calling [FltReleaseContext](nf-fltkernel-fltreleasecontext.md) to release this context when it is no longer needed.

## -returns

**FltAllocateContext** returns **STATUS_SUCCESS** or an appropriate **NTSTATUS** value, such as one of the following.

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
<b>FltAllocateContext</b> returns this status if either of the following conditions occur:
<ul>
<li>The allocation information for the context of the specified type was not provided at the time of filter registration.
<li>For fixed-size contexts, the requested <i>ContextSize</i> is greater than the <i>Size</i> specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a> structure for the specified <i>ContextType</i>.
</ul>
This is an error code.
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a> encountered a pool allocation failure. This is an error code.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
<i>ContextSize</i> cannot be greater than <b>MAXUSHORT</b>. This is an error code.
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

**FltAllocateContext** allocates a context of the specified type from the specified pool. The contents of the returned context are not zeroed.

After the context is allocated, it can be set on an object by passing the *ReturnedContext* pointer to the appropriate set-context routine from the following table.

| Context Type | Set-Context Routine |
| ------------ | ------------------- |
| FLT_FILE_CONTEXT | [FltSetFileContext](nf-fltkernel-fltsetfilecontext.md) (starting with Windows Vista) |
| FLT_INSTANCE_CONTEXT | [FltSetInstanceContext](nf-fltkernel-fltsetinstancecontext.md) |
| FLT_SECTION_CONTEXT | [FltCreateSectionForDataScan](nf-fltkernel-fltcreatesectionfordatascan.md) (Windows 8 and later only) |
| FLT_STREAM_CONTEXT | [FltSetStreamContext](nf-fltkernel-fltsetstreamcontext.md) |
| FLT_STREAMHANDLE_CONTEXT | [FltSetStreamHandleContext](nf-fltkernel-fltsetstreamhandlecontext.md) |
| FLT_TRANSACTION_CONTEXT | [FltSetTransactionContext](nf-fltkernel-fltsettransactioncontext.md) (starting with Windows Vista) |
| FLT_VOLUME_CONTEXT | [FltSetVolumeContext](nf-fltkernel-fltsetvolumecontext.md) |

When a minifilter driver calls [FltRegisterFilter](nf-fltkernel-fltregisterfilter.md) from its **DriverEntry** routine, it must register each context type that it uses. For more information, see the reference entry for the [FLT_CONTEXT_REGISTRATION](ns-fltkernel-_flt_context_registration.md) structure.

**FltAllocateContext** does not initialize the contents of the portion of the context structure specific to the minifilter driver.

To get the context for an object, call [FltGetContexts](nf-fltkernel-fltgetcontexts.md) or the appropriate get-context routine from the following table.

| Context Type | Get-Context Routine |
| ------------ | ------------------- |
| FLT_FILE_CONTEXT | [FltGetFileContext](nf-fltkernel-fltgetfilecontext.md) (starting with Windows Vista) |
| FLT_INSTANCE_CONTEXT | [FltGetInstanceContext](nf-fltkernel-fltgetinstancecontext.md) |
| FLT_SECTION_CONTEXT | [FltGetSectionContext](nf-fltkernel-fltgetsectioncontext.md) (starting with Windows 8) |
| FLT_STREAM_CONTEXT | [FltGetStreamContext](nf-fltkernel-fltgetstreamcontext.md) |
| FLT_STREAMHANDLE_CONTEXT | [FltGetStreamHandleContext](nf-fltkernel-fltgetstreamhandlecontext.md) |
| FLT_TRANSACTION_CONTEXT | [FltGetTransactionContext](nf-fltkernel-fltgettransactioncontext.md) (starting with Windows Vista ) |
| FLT_VOLUME_CONTEXT | [FltGetVolumeContext](nf-fltkernel-fltgetvolumecontext.md) |

Contexts are reference-counted, and on a successful return from **FltAllocateContext**, the context pointed to by *ReturnedContext* has a reference count of 1. A context is freed automatically when its reference count reaches zero. To increment the reference count on a context, call [FltReferenceContext](nf-fltkernel-fltreferencecontext).

To decrement the reference count on a context, call [FltReleaseContext](nf-fltkernel-fltreleasecontext.md).

Because contexts are reference-counted, it is not usually necessary to delete them. To delete a context explicitly, call [FltDeleteContext](nf-fltkernel-fltdeletecontext.md) or the appropriate delete-context routine from the following table.

| Context Type | Delete-Context Routine |
| ------------ | ---------------------- |
| FLT_FILE_CONTEXT | [FltDeleteFileContext](nf-fltkernel-fltdeletefilecontext.md) (starting with Windows Vista) |
| FLT_INSTANCE_CONTEXT | [FltDeleteInstanceContext](nf-fltkernel-fltdeleteinstancecontext.md) |
| FLT_SECTION_CONTEXT | [FltCloseSectionForDataScan](nf-fltkernel-fltclosesectionfordatascan.md) (starting with Windows 8) |
| FLT_STREAM_CONTEXT | [FltDeleteStreamContext](nf-fltkernel-fltdeletestreamcontext.md) |
| FLT_STREAMHANDLE_CONTEXT | [FltDeleteStreamHandleContext](nf-fltkernel-fltdeletestreamhandlecontext.md) |
| FLT_TRANSACTION_CONTEXT | [FltDeleteTransactionContext](nf-fltkernel-fltdeletetransactioncontext.md) (starting with Windows Vista) |
| FLT_VOLUME_CONTEXT | [FltDeleteVolumeContext](nf-fltkernel-fltdeletevolumecontext.md) |

## -see-also

[FLT_CONTEXT_REGISTRATION](ns-fltkernel-_flt_context_registration.md)

[FltCloseSectionForDataScan](nf-fltkernel-fltclosesectionfordatascan.md)

[FltCreateSectionForDataScan](nf-fltkernel-fltcreatesectionfordatascan.md)

[FltDeleteContext](nf-fltkernel-fltdeletecontext.md)

[FltDeleteFileContext](nf-fltkernel-fltdeletefilecontext.md)

[FltDeleteInstanceContext](nf-fltkernel-fltdeleteinstancecontext.md)

[FltDeleteStreamContext](nf-fltkernel-fltdeletestreamcontext.md)

[FltDeleteStreamHandleContext](nf-fltkernel-fltdeletestreamhandlecontext.md)

[FltDeleteTransactionContext](nf-fltkernel-fltdeletetransactioncontext.md)

[FltDeleteVolumeContext](nf-fltkernel-fltdeletevolumecontext.md)

[FltGetContexts](nf-fltkernel-fltgetcontexts.md)

[FltGetFileContext](nf-fltkernel-fltgetfilecontext.md)

[FltGetInstanceContext](nf-fltkernel-fltgetinstancecontext.md)

[FltGetSectionContext](nf-fltkernel-fltgetsectioncontext.md)

[FltGetStreamContext](nf-fltkernel-fltgetstreamcontext.md)

[FltGetStreamHandleContext](nf-fltkernel-fltgetstreamhandlecontext.md)

[FltGetTransactionContext](nf-fltkernel-fltgettransactioncontext.md)

[FltGetVolumeContext](nf-fltkernel-fltgetvolumecontext.md)

[FltReferenceContext](nf-fltkernel-fltreferencecontext.md)

[FltRegisterFilter](nf-fltkernel-fltregisterfilter.md)

[FltReleaseContext](nf-fltkernel-fltreleasecontext.md)

[FltSetFileContext](nf-fltkernel-fltsetfilecontext.md)

[FltSetInstanceContext](nf-fltkernel-fltsetinstancecontext.md)

[FltSetStreamContext](nf-fltkernel-fltsetstreamcontext.md)

[FltSetStreamHandleContext](nf-fltkernel-fltsetstreamhandlecontext.md)

[FltSetTransactionContext](nf-fltkernel-fltsettransactioncontext.md)

[FltSetVolumeContext](nf-fltkernel-fltsetvolumecontext.md)
