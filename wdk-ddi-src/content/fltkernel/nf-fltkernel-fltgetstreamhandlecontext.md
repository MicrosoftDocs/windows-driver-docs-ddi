---
UID: NF:fltkernel.FltGetStreamHandleContext
title: FltGetStreamHandleContext function
author: windows-driver-content
description: The FltGetStreamHandleContext routine retrieves a context that was set for a stream handle by a given minifilter driver instance.
old-location: ifsk\fltgetstreamhandlecontext.htm
old-project: ifsk
ms.assetid: c6e7c0d8-8005-4a40-a13b-ee58feeabbf0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_4a329c48-3a48-47bc-b998-3aaee454fbef.xml, FltGetStreamHandleContext, FltGetStreamHandleContext routine [Installable File System Drivers], fltkernel/FltGetStreamHandleContext, ifsk.fltgetstreamhandlecontext
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
-	FltGetStreamHandleContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetStreamHandleContext function


## -description


The <b>FltGetStreamHandleContext</b> routine retrieves a context that was set for a stream handle by a given minifilter driver instance. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance whose context is to be retrieved. 


### -param FileObject [in]

Pointer to a file object for the stream handle. 


### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the context. 


## -returns



<b>FltGetStreamHandleContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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



<b>FltGetStreamHandleContext</b> retrieves a context that was set for a stream handle by a given minifilter driver. 

<b>FltGetStreamHandleContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. Thus every successful call to <b>FltGetStreamHandleContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for a stream handle, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To delete a stream handle context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>
 

 

