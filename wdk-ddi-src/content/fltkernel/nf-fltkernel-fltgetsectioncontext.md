---
UID: NF:fltkernel.FltGetSectionContext
title: FltGetSectionContext function
author: windows-driver-content
description: The FltGetSectionContext routine retrieves a section context that was created for a file stream by a specified minifilter driver instance.
old-location: ifsk\fltgetsectioncontext.htm
old-project: ifsk
ms.assetid: 0B5C1BF9-59C3-4AC9-B545-FD7260B75E90
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltGetSectionContext, FltGetSectionContext routine [Installable File System Drivers], fltkernel/FltGetSectionContext, ifsk.fltgetsectioncontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetSectionContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetSectionContext function


## -description


The <b>FltGetSectionContext</b> routine retrieves a section context that was created for a file stream by a specified minifilter driver instance. 


## -syntax


````
NTSTATUS FltGetSectionContext(
  _In_  PFLT_INSTANCE Instance,
  _In_  PFILE_OBJECT  FileObject,
  _Out_ PFLT_CONTEXT  *Context
);
````


## -parameters




### -param Instance [in]

An opaque instance pointer for the minifilter driver instance whose context is to be retrieved. 


### -param FileObject [in]

A pointer to a file object for the stream. 


### -param Context [out]

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



<b>FltGetSectionContext</b> retrieves a section context that was created for a file stream by a specified minifilter driver instance. A section context is created by calling <a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a>.

<b>FltGetSectionContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. Thus every successful call to <b>FltGetSectionContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

<div class="alert"><b>Important</b>  <p class="note">Minifilters must not explicitly delete a section context passed to <a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a>. A section context is deallocated and removed from a stream  by calling <a href="..\fltkernel\nf-fltkernel-fltclosesectionfordatascan.md">FltCloseSectionForDataScan</a> in this case.

</div>
<div> </div>



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltclosesectionfordatascan.md">FltCloseSectionForDataScan</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetSectionContext routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

