---
UID: NF:fltkernel.FltSetStreamHandleContext
title: FltSetStreamHandleContext function
author: windows-driver-content
description: The FltSetStreamHandleContext routine sets a context for a stream handle.
old-location: ifsk\fltsetstreamhandlecontext.htm
old-project: ifsk
ms.assetid: 92c75e9c-ea29-40f5-84b2-bfe406075717
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_371045bc-91b4-4695-a44a-7ef4fd5c1bd7.xml, FltSetStreamHandleContext, FltSetStreamHandleContext routine [Installable File System Drivers], fltkernel/FltSetStreamHandleContext, ifsk.fltsetstreamhandlecontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available nor supported on Windows 2000 SP4 and earlier operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltSetStreamHandleContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetStreamHandleContext function


## -description


The <b>FltSetStreamHandleContext</b> routine sets a context for a stream handle. 


## -parameters




### -param Instance [in]

An opaque instance pointer for the minifilter driver instance whose context is to be inserted into, removed from, or replaced in the list of contexts attached to the stream handle. 


### -param FileObject [in]

A pointer to a file object for the file stream. 


### -param Operation [in]

A flag that specifies details of the operation to be performed. This parameter must be one of the following: 





#### FLT_SET_CONTEXT_REPLACE_IF_EXISTS

If a context is already set for this <i>Instance</i>, replace it with <i>NewContext</i>. Otherwise, insert <i>NewContext</i> into the list of contexts for the stream handle. 



#### FLT_SET_CONTEXT_KEEP_IF_EXISTS

If a context is already set for this <i>Instance</i>, return STATUS_FLT_CONTEXT_ALREADY_DEFINED. Otherwise, insert <i>NewContext</i> into the list of contexts for the stream handle. 


### -param NewContext [in]

A pointer to the new context to be set for the stream handle. This parameter is required and cannot be <b>NULL</b>. 


### -param OldContext [out, optional]

A pointer to a caller-allocated variable that receives the address of the existing stream handle context for the <i>Instance </i>parameter. This parameter is optional and can be <b>NULL</b>. (For more information about this parameter, see the following Remarks section.) 


## -returns



The <b>FltSetStreamHandleContext</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
If FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for <i>Operation</i>, this error code indicates that a context is already attached to the stream handle.  

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_LINKED</b></dt>
</dl>
</td>
<td width="60%">
The context pointed to by the <i>NewContext</i> parameter is already linked to an object.  In other words, this error code indicates that <i>NewContext</i> is already in use due to a successful prior call of a  <b>FltSet</b><i>Xxx</i><b>Context</b> routine. 

</td>
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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the following: 

<ul>
<li>
The <i>NewContext</i> parameter does not point to a valid stream handle context. 

</li>
<li>
An invalid value was specified for <i>Operation</i>. 

</li>
</ul>
STATUS_INVALID_PARAMETER is an error code.

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



The <b>FltSetStreamHandleContext</b> routine adds, removes, or replaces a context for a minifilter driver instance on a stream handle. A minifilter driver can attach one context per minifilter driver instance to the stream handle. 

A successful call to <b>FltSetStreamHandleContext</b> increments the reference count on <i>NewContext</i>. When the context pointed to by <i>NewContext</i> is no longer needed, the minifilter must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> to decrement its reference count.



If <b>FltSetStreamHandleContext</b> fails, the reference count remains unchanged. In this case, the filter calling <b>FltSetStreamHandleContext</b> must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> for the <i>NewContext</i> object that was allocated and referenced in <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. If <b>FltSetStreamHandleContext</b> fails and if the <i>OldContext</i> parameter is not <b>NULL</b> and does not point to NULL_CONTEXT then <i>OldContext</i> is a referenced pointer to the context currently associated with the transaction. The filter calling <b>FltSetStreamHandleContext</b> must call <b>FltReleaseContext</b> for <i>OldContext</i> as well.



Note that the <i>OldContext</i> pointer returned by <b>FltSetStreamHandleContext</b> must also be released by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> when it is no longer needed. For more information, see <a href="https://msdn.microsoft.com/3daa23e6-14d7-4d35-8bc8-695296cd289d">Setting Contexts</a> and <a href="https://msdn.microsoft.com/29d855cd-cca6-486b-86d9-f74810ae12c1">Releasing Contexts</a>. 

Also note that <b>FltSetStreamHandleContext</b> cannot be called on an unopened <i>FileObject</i>. Hence <b>FltSetStreamHandleContext</b> cannot be called from a pre-create callback for a stream because the stream has not been opened at that point. A minifilter can, however, allocate and set up the stream handle context in the pre-create callback, pass it to the post-create callback using the completion context parameter and set the stream handle context on the stream in the post-create callback. 

To get a stream handle context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To delete a stream handle context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>
 

 

