---
UID: NF:fltkernel.FltDeleteStreamContext
title: FltDeleteStreamContext function
author: windows-driver-content
description: FltDeleteStreamContext removes a context that a given minifilter driver instance has set for a given stream and marks the context for deletion.
old-location: ifsk\fltdeletestreamcontext.htm
tech.root: ifsk
ms.assetid: 49f7d633-3e8b-4c9c-b14a-7ae8f997ad2f
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_8339a254-56eb-4f75-b294-006286f3ff10.xml, FltDeleteStreamContext, FltDeleteStreamContext function [Installable File System Drivers], fltkernel/FltDeleteStreamContext, ifsk.fltdeletestreamcontext
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltDeleteStreamContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltDeleteStreamContext function


## -description


<b>FltDeleteStreamContext</b> removes a context that a given minifilter driver instance has set for a given stream and marks the context for deletion. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance whose context is to be removed from the list of contexts attached to the file stream. 


### -param FileObject [in]

Pointer to a file object for the file stream. 


### -param OldContext [out]

Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> to release this context when it is no longer needed. 


## -returns



<b>FltDeleteStreamContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Instance</i> is being torn down. This is an error code. 

</td>
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



Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteStreamContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteStreamContext</b> to remove a context from a file stream and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still in use by another thread). 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To get a stream context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543144">FltGetStreamContext</a>. 

To set a stream context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543144">FltGetStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>
 

 

