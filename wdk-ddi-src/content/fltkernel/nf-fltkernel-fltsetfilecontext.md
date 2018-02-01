---
UID: NF:fltkernel.FltSetFileContext
title: FltSetFileContext function
author: windows-driver-content
description: The FltSetFileContext routine sets a context for a file.
old-location: ifsk\fltsetfilecontext.htm
old-project: ifsk
ms.assetid: d56cb216-a757-4ab8-ac7f-04dc22997835
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltSetFileContext, FltApiRef_p_to_z_ef77cece-4fd9-4453-9594-b027037d3ca9.xml, fltkernel/FltSetFileContext, ifsk.fltsetfilecontext, FltSetFileContext routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported starting with Windows Vista. For more information, see the Remarks section.
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltSetFileContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetFileContext function


## -description


The <b>FltSetFileContext</b> routine sets a context for a file. 


## -syntax


````
NTSTATUS FltSetFileContext(
  _In_  PFLT_INSTANCE             Instance,
  _In_  PFILE_OBJECT              FileObject,
  _In_  FLT_SET_CONTEXT_OPERATION Operation,
  _In_  PFLT_CONTEXT              NewContext,
  _Out_ PFLT_CONTEXT              *OldContext
);
````


## -parameters




### -param Instance [in]

An opaque pointer to a minifilter driver instance for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

A file object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param Operation [in]

A flag that specifies the type of operation for <b>FltSetFileContext </b>to perform. This parameter must be one of the following flags:  




#### FLT_SET_CONTEXT_KEEP_IF_EXISTS

If a context is already set for the instance that the <i>Instance</i> parameter points to, <b>FltSetFileContext</b> will return STATUS_FLT_CONTEXT_ALREADY_DEFINED. Otherwise, the routine will insert the context specified in <i>NewContext</i> into the list of contexts for the file. 


#### FLT_SET_CONTEXT_REPLACE_IF_EXISTS

If a context is already set for the instance that the <i>Instance </i>parameter points to, <b>FltSetFileContext</b> will replace that context with the context specified in <i>NewContext</i>. Otherwise, the routine will insert the context specified in <i>NewContext</i> into the list of contexts for the file. 


### -param NewContext [in]

A pointer to the new context to be set for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param OldContext [out]

A pointer to a caller-allocated variable that receives the address of the existing file context for the instance pointed to by the <i>Instance </i>parameter. This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section. 


## -returns


The <b>FltSetFileContext</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_DEFINED</b></dt>
</dl>
</td>
<td width="60%">
If FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for the <i>Operation</i> parameter, this error code indicates that a context is already attached to the file. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_LINKED</b></dt>
</dl>
</td>
<td width="60%">
The context pointed to by the <i>NewContext</i> parameter is already linked to an object.  In other words, this error code indicates that <i>NewContext</i> is already in use due to a successful prior call of a <b>FltSet</b><i>Xxx</i><b>Context</b> routine. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The instance specified in the <i>Instance</i> parameter is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This error code indicates one of the following problems:

<ul>
<li>
The <i>NewContext</i> parameter does not point to a valid file context. 

</li>
<li>
An invalid value was specified for the <i>Operation</i> parameter. 

</li>
</ul>
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


The <b>FltSetFileContext</b> routine is available on Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. This routine is available and supported starting with Windows Vista (file contexts are only supported starting with Windows Vista). If <b>FltSetFileContext</b> is called on an operating system where this routine is available but file contexts are not supported, it returns STATUS_NOT_SUPPORTED.  This routine is not available on Windows 2000 SP4 and earlier operating systems.

A minifilter driver calls <b>FltSetFileContext</b> to set or replace its own file context on a file. A minifilter driver can attach one context per minifilter driver instance to the file. 

A successful call to <b>FltSetFileContext</b> increments the reference count on <i>NewContext</i>. If <b>FltSetFileContext</b> fails, the reference count remains unchanged. In either case, the filter calling <b>FltSetFileContext</b> must call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> to decrement the <i>NewContext</i> object. If <b>FltSetFileContext</b> fails and if the <i>OldContext</i> parameter is not <b>NULL</b> and does not point to NULL_CONTEXT then <i>OldContext</i> is a referenced pointer to the context currently associated with the transaction. The filter calling <b>FltSetFileContext</b> must call <b>FltReleaseContext</b> for <i>OldContext</i> as well.

Note that the <i>OldContext</i> pointer returned by <b>FltSetFileContext</b> must also be released by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> when it is no longer needed. For more information, see <a href="https://msdn.microsoft.com/3daa23e6-14d7-4d35-8bc8-695296cd289d">Setting Contexts</a> and <a href="https://msdn.microsoft.com/29d855cd-cca6-486b-86d9-f74810ae12c1">Releasing Contexts</a>.

Be aware that <b>FltSetFileContext</b> cannot be called on an unopened <i>FileObject</i>. Hence <b>FltSetFileContext</b> cannot be called from a pre-create callback for a stream because the stream has not been opened at that point. A minifilter driver can, however, allocate and set up the stream file context in the pre-create callback, pass it to the post-create callback using the completion context parameter and set the stream file context on the file corresponding to that stream in the post-create callback.

To get a file context, call <a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a>. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To delete a file context, call <a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 

To determine whether file contexts are supported for a given file, call <a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontexts.md">FltSupportsFileContexts</a> or <a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontextsex.md">FltSupportsFileContextsEx</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>. 



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a>

<a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontextsex.md">FltSupportsFileContextsEx</a>

<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>

<a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontexts.md">FltSupportsFileContexts</a>

<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>

<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>

<a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetFileContext routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

