---
UID: NF:fltkernel.FltGetFileContext
title: FltGetFileContext function (fltkernel.h)
description: The FltGetFileContext routine retrieves a context that was set for a file by a given minifilter driver instance.
old-location: ifsk\fltgetfilecontext.htm
tech.root: ifsk
ms.assetid: 3104cccf-03ae-4ff9-8cfe-86bd3719a47f
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_230a0040-01b0-4998-8f16-427eec529aee.xml, FltGetFileContext, FltGetFileContext routine [Installable File System Drivers], fltkernel/FltGetFileContext, ifsk.fltgetfilecontext
ms.topic: function
f1_keywords:
 - "fltkernel/FltGetFileContext"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows Vista and later.
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
- FltGetFileContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetFileContext function


## -description


The <b>FltGetFileContext</b> routine retrieves a context that was set for a file by a given minifilter driver instance. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the context. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetFileContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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



A minifilter driver calls <b>FltGetFileContext</b> to retrieve the file context that it has set for a given file. 

To decrement the reference count on a context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>. 

<b>FltGetFileContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. Thus, every successful call to <b>FltGetFileContext</b> must be matched by a subsequent call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>. 

To set a file context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetfilecontext">FltSetFileContext</a>. 

To allocate a new context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To delete a file context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletefilecontext">FltDeleteFileContext</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>. 

To determine whether file contexts are supported for a given file, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontexts">FltSupportsFileContexts</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontextsex">FltSupportsFileContextsEx</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletefilecontext">FltDeleteFileContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetfilecontext">FltSetFileContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontexts">FltSupportsFileContexts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontextsex">FltSupportsFileContextsEx</a>
 

 

