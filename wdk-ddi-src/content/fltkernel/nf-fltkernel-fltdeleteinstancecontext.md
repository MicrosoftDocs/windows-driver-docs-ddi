---
UID: NF:fltkernel.FltDeleteInstanceContext
title: FltDeleteInstanceContext function
author: windows-driver-content
description: FltDeleteInstanceContext removes a context from a given instance and marks the context for deletion.
old-location: ifsk\fltdeleteinstancecontext.htm
old-project: ifsk
ms.assetid: 910b62d7-2ef3-4eb2-97c3-9b920fdb0558
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_2ccc7fef-0bff-4df4-b617-fb4749bb3ed6.xml, FltDeleteInstanceContext, FltDeleteInstanceContext function [Installable File System Drivers], fltkernel/FltDeleteInstanceContext, ifsk.fltdeleteinstancecontext
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
-	FltDeleteInstanceContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltDeleteInstanceContext function


## -description


<b>FltDeleteInstanceContext</b> removes a context from a given instance and marks the context for deletion. 


## -syntax


````
NTSTATUS FltDeleteInstanceContext(
  _In_  PFLT_INSTANCE Instance,
  _Out_ PFLT_CONTEXT  *OldContext
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the instance. 


### -param OldContext [out]

Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> to release this context when it is no longer needed. 


## -returns



<b>FltDeleteInstanceContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
</table>
 




## -remarks



Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteInstanceContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteInstanceContext</b> to remove a context from an instance and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To get an instance context, call <a href="..\fltkernel\nf-fltkernel-fltgetinstancecontext.md">FltGetInstanceContext</a>. 

To set an instance context, call <a href="..\fltkernel\nf-fltkernel-fltsetinstancecontext.md">FltSetInstanceContext</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetinstancecontext.md">FltSetInstanceContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetinstancecontext.md">FltGetInstanceContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeleteInstanceContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

