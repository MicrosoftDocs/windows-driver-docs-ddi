---
UID: NF:fltkernel.FltGetSectionContext
title: FltGetSectionContext function (fltkernel.h)
description: The FltGetSectionContext routine retrieves a section context that was created for a file stream by a specified minifilter driver instance.
old-location: ifsk\fltgetsectioncontext.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltGetSectionContext function"]
ms.keywords: FltGetSectionContext, FltGetSectionContext routine [Installable File System Drivers], fltkernel/FltGetSectionContext, ifsk.fltgetsectioncontext
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltGetSectionContext routine is available starting with  Windows 8.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetSectionContext
 - fltkernel/FltGetSectionContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetSectionContext
---

# FltGetSectionContext function


## -description

The <b>FltGetSectionContext</b> routine retrieves a section context that was created for a file stream by a specified minifilter driver instance.

## -parameters

### -param Instance 

[in]
An opaque instance pointer for the minifilter driver instance whose context is to be retrieved.

### -param FileObject 

[in]
A pointer to a file object for the stream.

### -param Context 

[out]
A pointer to a caller-allocated variable that receives the address of the context.

## -returns

<b>FltGetSectionContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching context was found. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The volume attached to this instance does not support section contexts. This is an error code. 

</td>
</tr>
</table>

## -remarks

<b>FltGetSectionContext</b> retrieves a section context that was created for a file stream by a specified minifilter driver instance. A section context is created by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatesectionfordatascan">FltCreateSectionForDataScan</a>.

<b>FltGetSectionContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>. Thus every successful call to <b>FltGetSectionContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To allocate a new context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

<div class="alert"><b>Important</b>  <p class="note">Minifilters must not explicitly delete a section context passed to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatesectionfordatascan">FltCreateSectionForDataScan</a>. A section context is deallocated and removed from a stream  by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclosesectionfordatascan">FltCloseSectionForDataScan</a> in this case.

</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclosesectionfordatascan">FltCloseSectionForDataScan</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatesectionfordatascan">FltCreateSectionForDataScan</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>
