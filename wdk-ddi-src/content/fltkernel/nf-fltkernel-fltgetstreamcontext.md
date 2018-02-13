---
UID: NF:fltkernel.FltGetStreamContext
title: FltGetStreamContext function
author: windows-driver-content
description: The FltGetStreamContext routine retrieves a context that was set for a file stream by a given minifilter driver instance.
old-location: ifsk\fltgetstreamcontext.htm
old-project: ifsk
ms.assetid: c076390d-42b0-4c8f-b9b1-9db910068795
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltApiRef_e_to_o_e7a12c32-5aec-433e-86e4-46844f56e75a.xml, FltGetStreamContext routine [Installable File System Drivers], fltkernel/FltGetStreamContext, ifsk.fltgetstreamcontext, FltGetStreamContext
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
-	FltGetStreamContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetStreamContext function


## -description


The <b>FltGetStreamContext</b> routine retrieves a context that was set for a file stream by a given minifilter driver instance. 


## -syntax


````
NTSTATUS FltGetStreamContext(
  _In_  PFLT_INSTANCE Instance,
  _In_  PFILE_OBJECT  FileObject,
  _Out_ PFLT_CONTEXT  *Context
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance whose context is to be retrieved. 


### -param FileObject [in]

Pointer to a file object for the stream. 


### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the context. 


## -returns



<b>FltGetStreamContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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
The file system does not support per-stream contexts for this file stream. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltGetStreamContext</b> retrieves a context that was set for a file stream by a given minifilter driver instance. 

<b>FltGetStreamContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. Thus every successful call to <b>FltGetStreamContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for a file stream, call <a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To delete a stream context, call <a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetStreamContext routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

