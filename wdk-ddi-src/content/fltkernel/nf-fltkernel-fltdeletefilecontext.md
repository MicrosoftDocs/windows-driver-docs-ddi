---
UID: NF:fltkernel.FltDeleteFileContext
title: FltDeleteFileContext function (fltkernel.h)
description: The FltDeleteFileContext routine retrieves and deletes a file context that a given minifilter driver has set for a given file.
old-location: ifsk\fltdeletefilecontext.htm
tech.root: ifsk
ms.assetid: faffa053-0382-415c-8f61-ee9121839598
ms.date: 04/16/2018
keywords: ["FltDeleteFileContext function"]
ms.keywords: FltApiRef_a_to_d_53ae4cfc-b70a-405d-b947-cb0f04d4663b.xml, FltDeleteFileContext, FltDeleteFileContext routine [Installable File System Drivers], fltkernel/FltDeleteFileContext, ifsk.fltdeletefilecontext
f1_keywords:
 - "fltkernel/FltDeleteFileContext"
 - "FltDeleteFileContext"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltDeleteFileContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltDeleteFileContext function


## -description


The <b>FltDeleteFileContext</b> routine retrieves and deletes a file context that a given minifilter driver has set for a given file. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param OldContext [out]

Pointer to a caller-allocated variable that receives the address of the deleted context. If no matching context is found, this variable receives NULL_CONTEXT. This parameter is optional and can be <b>NULL</b>. (For more information about this parameter, see the following Remarks section.) 


## -returns



<b>FltDeleteFileContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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
File contexts are not supported for this file. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



The <b>FltDeleteFileContext</b> routine is available on Windows Vista and later. 

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteFileContext</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteFileContext</b> to retrieve and delete a file context that it previously set for a file by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetfilecontext">FltSetFileContext</a>. 

If the <i>OldContext</i> parameter is <b>NULL</b> on input and a matching file context is found, <b>FltDeleteFileContext</b> releases the reference that was added by the minifilter driver's previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetfilecontext">FltSetFileContext</a>. The deleted context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

If the <i>OldContext</i> parameter is not <b>NULL</b> and a matching file context is found and returned, the caller is responsible for releasing the reference that was added by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetfilecontext">FltSetFileContext</a>. To release this reference, the minifilter driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> on the deleted file context as soon as possible after performing any necessary cleanup. 

To allocate a new context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To decrement the reference count on a context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>. 

To delete a context for which you already have a context pointer, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>. 

To retrieve a file context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilecontext">FltGetFileContext</a>. 

To set a file context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetfilecontext">FltSetFileContext</a>. 

To determine whether file contexts are supported for a given file, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontexts">FltSupportsFileContexts</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontextsex">FltSupportsFileContextsEx</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilecontext">FltGetFileContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetfilecontext">FltSetFileContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontexts">FltSupportsFileContexts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontextsex">FltSupportsFileContextsEx</a>
 

 

