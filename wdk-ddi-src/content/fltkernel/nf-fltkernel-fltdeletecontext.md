---
UID: NF:fltkernel.FltDeleteContext
title: FltDeleteContext function
author: windows-driver-content
description: FltDeleteContext marks a specified context for deletion.
old-location: ifsk\fltdeletecontext.htm
tech.root: ifsk
ms.assetid: 1cdb0747-7616-414b-8287-1ef73637ed05
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_d4c075e6-7a69-4d2f-9017-eccbf55eb9e0.xml, FltDeleteContext, FltDeleteContext function [Installable File System Drivers], fltkernel/FltDeleteContext, ifsk.fltdeletecontext
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltDeleteContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltDeleteContext function


## -description


<b>FltDeleteContext</b> marks a specified context for deletion. 


## -parameters




### -param Context [in]

A pointer to the context to delete. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None. 




## -remarks



Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine, such as <b>FltDeleteContext</b>, to explicitly delete a context. 

<b>FltDeleteContext</b> marks a context for deletion. The context is usually freed as soon as the current reference on it is released, unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

You should consider the following items when you use <b>FltDeleteContext</b>:

<ul>
<li>
When a minifilter driver calls <b>FltDeleteContext</b>, the minifilter driver must already have a reference to the context. However, when the minifilter driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541982">FltDeleteInstanceContext</a>, and so on, the minifilter driver does not require a reference to the context. After the minifilter driver calls <b>FltDeleteContext</b>, that reference to the context is still valid. The minifilter driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> routine to release the reference to the context. 

</li>
<li>
<b>FltDeleteContext</b> removes the context from the internal filter manager structures. Then, further calls to functions that retrieve contexts, such as  <a href="https://msdn.microsoft.com/library/windows/hardware/ff542997">FltGetContexts</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543058">FltGetInstanceContext</a>, cannot locate that context. However, the context memory is not released until the reference count for the context goes to 0. 

</li>
</ul>
Contexts can also be deleted by calling the appropriate delete-context routine from the following table. 

<table>
<tr>
<th>Context Type</th>
<th>Delete-Context Routine</th>
</tr>
<tr>
<td>
FLT_FILE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541980">FltDeleteFileContext</a> (Windows Vista and later only.)

</td>
</tr>
<tr>
<td>
FLT_INSTANCE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541982">FltDeleteInstanceContext</a>


</td>
</tr>
<tr>
<td>
FLT_SECTION_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406456">FltCloseSectionForDataScan</a> (Windows 8 and later only.)

</td>
</tr>
<tr>
<td>
FLT_STREAM_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a>


</td>
</tr>
<tr>
<td>
FLT_STREAMHANDLE_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>


</td>
</tr>
<tr>
<td>
FLT_TRANSACTION_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a> (Windows Vista and later only.)

</td>
</tr>
<tr>
<td>
FLT_VOLUME_CONTEXT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542030">FltDeleteVolumeContext</a>


</td>
</tr>
</table>
 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To increment the reference count on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544291">FltReferenceContext</a>. 

To decrement the reference count on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. 

A section context, FLT_SECTION_CONTEXT type, must not be deleted using <b>FltDeleteContext</b>. Instead, use  <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> to deallocate a section context.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406456">FltCloseSectionForDataScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541980">FltDeleteFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541982">FltDeleteInstanceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542023">FltDeleteTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542030">FltDeleteVolumeContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544291">FltReferenceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>
 

 

