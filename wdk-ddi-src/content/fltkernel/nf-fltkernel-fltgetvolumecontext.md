---
UID: NF:fltkernel.FltGetVolumeContext
title: FltGetVolumeContext function (fltkernel.h)
description: The FltGetVolumeContext routine retrieves a context that was set for a volume by a given minifilter driver.
old-location: ifsk\fltgetvolumecontext.htm
tech.root: ifsk
ms.assetid: daa7d15f-580a-4668-9159-834e18b28c1f
ms.date: 04/16/2018
keywords: ["FltGetVolumeContext function"]
ms.keywords: FltApiRef_e_to_o_8cec5d5c-18c3-4ffe-be18-fffcfc8d0c14.xml, FltGetVolumeContext, FltGetVolumeContext routine [Installable File System Drivers], fltkernel/FltGetVolumeContext, ifsk.fltgetvolumecontext
f1_keywords:
 - "fltkernel/FltGetVolumeContext"
 - "FltGetVolumeContext"
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
- FltGetVolumeContext
targetos: Windows
req.typenames: 
---

# FltGetVolumeContext function


## -description


The <b>FltGetVolumeContext</b> routine retrieves a context that was set for a volume by a given minifilter driver. 


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param Volume [in]

Opaque pointer for the volume whose context is being retrieved. This parameter is required and cannot be <b>NULL</b>. 


### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the requested context. 


## -returns



<b>FltGetVolumeContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

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
</table>
 




## -remarks



<b>FltGetVolumeContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>. Thus every successful call to <b>FltGetVolumeContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for a volume, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumecontext">FltSetVolumeContext</a>. 

To allocate a new context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To delete a volume context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletevolumecontext">FltDeleteVolumeContext</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletevolumecontext">FltDeleteVolumeContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumecontext">FltSetVolumeContext</a>
 

 

