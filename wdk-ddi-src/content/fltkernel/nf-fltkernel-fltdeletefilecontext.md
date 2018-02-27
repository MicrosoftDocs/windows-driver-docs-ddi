---
UID: NF:fltkernel.FltDeleteFileContext
title: FltDeleteFileContext function
author: windows-driver-content
description: The FltDeleteFileContext routine retrieves and deletes a file context that a given minifilter driver has set for a given file.
old-location: ifsk\fltdeletefilecontext.htm
old-project: ifsk
ms.assetid: faffa053-0382-415c-8f61-ee9121839598
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_53ae4cfc-b70a-405d-b947-cb0f04d4663b.xml, FltDeleteFileContext, FltDeleteFileContext routine [Installable File System Drivers], fltkernel/FltDeleteFileContext, ifsk.fltdeletefilecontext
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltDeleteFileContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltDeleteFileContext function


## -description


The <b>FltDeleteFileContext</b> routine retrieves and deletes a file context that a given minifilter driver has set for a given file. 


## -syntax


````
NTSTATUS FltDeleteFileContext(
  _In_  PFLT_INSTANCE Instance,
  _In_  PFILE_OBJECT  FileObject,
  _Out_ PFLT_CONTEXT  *OldContext
);
````


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

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteFileContext</b> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteFileContext</b> to retrieve and delete a file context that it previously set for a file by calling <a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>. 

If the <i>OldContext</i> parameter is <b>NULL</b> on input and a matching file context is found, <b>FltDeleteFileContext</b> releases the reference that was added by the minifilter driver's previous call to <a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>. The deleted context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

If the <i>OldContext</i> parameter is not <b>NULL</b> and a matching file context is found and returned, the caller is responsible for releasing the reference that was added by <a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>. To release this reference, the minifilter driver must call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> on the deleted file context as soon as possible after performing any necessary cleanup. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To decrement the reference count on a context, call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. 

To delete a context for which you already have a context pointer, call <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 

To retrieve a file context, call <a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a>. 

To set a file context, call <a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>. 

To determine whether file contexts are supported for a given file, call <a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontexts.md">FltSupportsFileContexts</a> or <a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontextsex.md">FltSupportsFileContextsEx</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontextsex.md">FltSupportsFileContextsEx</a>



<a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontexts.md">FltSupportsFileContexts</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeleteFileContext routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

