---
UID: NF:fltkernel.FltSupportsFileContextsEx
title: FltSupportsFileContextsEx function (fltkernel.h)
description: The FltSupportsFileContextsEx routine determines whether the file system or the filter manager support file contexts for a given file.
old-location: ifsk\fltsupportsfilecontextsex.htm
tech.root: ifsk
ms.assetid: 42401474-ea2d-441f-ad70-bd95544933ac
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_3e8b5485-5c61-4405-9c5d-7d7c966f0478.xml, FltSupportsFileContextsEx, FltSupportsFileContextsEx routine [Installable File System Drivers], fltkernel/FltSupportsFileContextsEx, ifsk.fltsupportsfilecontextsex
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
-	FltSupportsFileContextsEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSupportsFileContextsEx function


## -description


The <b>FltSupportsFileContextsEx</b> routine determines whether the file system or the filter manager support file contexts for a given file. 


## -parameters




### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param Instance [in, optional]

Opaque instance pointer for the caller. This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section. 


## -returns



<b>FltSupportsFileContextsEx</b> returns <b>TRUE</b> if the file system or filter manager supports file contexts for the file; <b>FALSE</b> otherwise. 




## -remarks



Minifilter drivers call the <b>FltSupportsFileContextsEx</b> routine to determine whether the underlying file system or the filter manager supports file contexts for the file that is represented by a given file object. 

For file systems (such as FAT) that support only a single data stream per file, file contexts are equivalent to stream contexts. Such file systems usually support stream contexts but do not support file contexts. Instead, the filter manager provides file context support, using the file system's existing support for stream contexts. For minifilter instances attached to these file systems, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544574">FltSupportsFileContexts</a> returns <b>FALSE</b>, while <b>FltSupportsFileContextsEx</b> returns <b>TRUE</b> (when a valid non-<b>NULL</b> value is passed for the <i>Instance</i> parameter). 

If a non-<b>NULL</b> value is supplied for the <i>Instance</i> parameter, <b>FltSupportsFileContextsEx</b> returns <b>TRUE</b> if the file system or the filter manager supports file contexts for the file; <b>FALSE</b> otherwise. 

If the <i>Instance</i> parameter is <b>NULL</b>, <b>FltSupportsFileContextsEx</b> returns <b>TRUE</b> only if the file system supports file contexts for the file. Otherwise, it returns <b>FALSE</b>, even if the filter manager supports file contexts for the file. 

Note that a file system might support file contexts for some types of files but not for others. For example, NTFS and FAT do not support file contexts for paging files. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To delete a file context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541980">FltDeleteFileContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 

To get the file context for a file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543025">FltGetFileContext</a>. 

To set a file context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>. 

To decrement the reference count on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541980">FltDeleteFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543025">FltGetFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544574">FltSupportsFileContexts</a>
 

 

