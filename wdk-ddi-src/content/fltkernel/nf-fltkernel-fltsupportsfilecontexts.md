---
UID: NF:fltkernel.FltSupportsFileContexts
title: FltSupportsFileContexts function
author: windows-driver-content
description: The FltSupportsFileContexts routine determines whether the file system supports file contexts for a given file.
old-location: ifsk\fltsupportsfilecontexts.htm
old-project: ifsk
ms.assetid: 968c2c6d-3544-45e7-b852-740fa4930349
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_cad3f45c-7ae0-44dc-840d-a8ec3da65ea6.xml, FltSupportsFileContexts, FltSupportsFileContexts routine [Installable File System Drivers], fltkernel/FltSupportsFileContexts, ifsk.fltsupportsfilecontexts
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
-	FltSupportsFileContexts
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSupportsFileContexts function


## -description


The <b>FltSupportsFileContexts</b> routine determines whether the file system supports file contexts for a given file. 


## -syntax


````
BOOLEAN FltSupportsFileContexts(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltSupportsFileContexts</b> returns <b>TRUE</b> if the file system supports file contexts for the file object; <b>FALSE</b> otherwise. 




## -remarks



Minifilter drivers call <b>FltSupportsFileContexts</b> to determine whether the underlying file system inherently supports file contexts for the file that is represented by a given file object. 

Note that a file system might support file contexts for some types of files but not for others. For example, NTFS and FAT do not support file contexts for paging files. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To delete a file context, call <a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 

To get the file context for a file object, call <a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a>. 

To set a file context, call <a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>. 

To decrement the reference count on a context, call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsetfilecontext.md">FltSetFileContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletefilecontext.md">FltDeleteFileContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilecontext.md">FltGetFileContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsupportsfilecontextsex.md">FltSupportsFileContextsEx</a>



 

 


