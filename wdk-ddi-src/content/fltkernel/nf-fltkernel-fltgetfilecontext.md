---
UID: NF:fltkernel.FltGetFileContext
title: FltGetFileContext function
author: windows-driver-content
description: The FltGetFileContext routine retrieves a context that was set for a file by a given minifilter driver instance.
old-location: ifsk\fltgetfilecontext.htm
old-project: ifsk
ms.assetid: 3104cccf-03ae-4ff9-8cfe-86bd3719a47f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_230a0040-01b0-4998-8f16-427eec529aee.xml, FltGetFileContext, FltGetFileContext routine [Installable File System Drivers], fltkernel/FltGetFileContext, ifsk.fltgetfilecontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetFileContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetFileContext function


## -description


The <b>FltGetFileContext</b> routine retrieves a context that was set for a file by a given minifilter driver instance. 


## -syntax


````
NTSTATUS FltGetFileContext(
  _In_  PFLT_INSTANCE Instance,
  _In_  PFILE_OBJECT  FileObject,
  _Out_ PFLT_CONTEXT  *Context
);
````


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

To decrement the reference count on a context, call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. 

<b>FltGetFileContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. Thus, every successful call to <b>FltGetFileContext</b> must be matched by a subsequent call to <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. 

To set a file context, call <a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To delete a file context, call <a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 

To determine whether file contexts are supported for a given file, call <a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontexts.md">FltSupportsFileContexts</a> or <a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontextsex.md">FltSupportsFileContextsEx</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>



<a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontexts.md">FltSupportsFileContexts</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontextsex.md">FltSupportsFileContextsEx</a>



 

 


