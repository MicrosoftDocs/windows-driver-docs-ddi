---
UID: NF:fltkernel.FltDeleteVolumeContext
title: FltDeleteVolumeContext function (fltkernel.h)
description: FltDeleteVolumeContext removes a context that a given minifilter driver has set for a given volume and marks the context for deletion.
old-location: ifsk\fltdeletevolumecontext.htm
tech.root: ifsk
ms.assetid: dfb376af-9910-4708-9248-1104dfc4bdec
ms.date: 04/16/2018
keywords: ["FltDeleteVolumeContext function"]
ms.keywords: FltApiRef_a_to_d_261f2efb-7c2e-4f85-a75c-b5cf55236271.xml, FltDeleteVolumeContext, FltDeleteVolumeContext function [Installable File System Drivers], fltkernel/FltDeleteVolumeContext, ifsk.fltdeletevolumecontext
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
 - FltDeleteVolumeContext
 - fltkernel/FltDeleteVolumeContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDeleteVolumeContext
---

# FltDeleteVolumeContext function


## -description

<b>FltDeleteVolumeContext</b> removes a context that a given minifilter driver has set for a given volume and marks the context for deletion.

## -parameters

### -param Filter 

[in]
Opaque filter pointer for the caller.

### -param Volume 

[in]
Opaque volume pointer for the volume.

### -param OldContext 

[out, optional]
Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> to release this context when it is no longer needed.

## -returns

<b>FltDeleteVolumeContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
The specified <i>Volume</i> is being torn down. This is an error code. 

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

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteVolumeContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteVolumeContext</b> to remove a context from a volume and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still in use by another thread). 

To allocate a new context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To get a volume context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumecontext">FltGetVolumeContext</a>. 

To set a volume context, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumecontext">FltSetVolumeContext</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumecontext">FltGetVolumeContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumecontext">FltSetVolumeContext</a>