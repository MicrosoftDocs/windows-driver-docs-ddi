---
UID: NF:fltkernel.FltDeleteInstanceContext
title: FltDeleteInstanceContext function (fltkernel.h)
description: FltDeleteInstanceContext removes a context from a given instance and marks the context for deletion.
old-location: ifsk\fltdeleteinstancecontext.htm
tech.root: ifsk
ms.assetid: 910b62d7-2ef3-4eb2-97c3-9b920fdb0558
ms.date: 04/16/2018
keywords: ["FltDeleteInstanceContext function"]
ms.keywords: FltApiRef_a_to_d_2ccc7fef-0bff-4df4-b617-fb4749bb3ed6.xml, FltDeleteInstanceContext, FltDeleteInstanceContext function [Installable File System Drivers], fltkernel/FltDeleteInstanceContext, ifsk.fltdeleteinstancecontext
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
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltDeleteInstanceContext
 - fltkernel/FltDeleteInstanceContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDeleteInstanceContext
---

# FltDeleteInstanceContext function


## -description

<b>FltDeleteInstanceContext</b> removes a context from a given instance and marks the context for deletion.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the instance.

### -param OldContext 

[out]
Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> to release this context when it is no longer needed.

## -returns

<b>FltDeleteInstanceContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Instance</i> is being torn down. This is an error code. 

</td>
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
</table>

## -remarks

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteInstanceContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteInstanceContext</b> to remove a context from an instance and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

To allocate a new context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To get an instance context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetinstancecontext">FltGetInstanceContext</a>. 

To set an instance context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinstancecontext">FltSetInstanceContext</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetinstancecontext">FltGetInstanceContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinstancecontext">FltSetInstanceContext</a>