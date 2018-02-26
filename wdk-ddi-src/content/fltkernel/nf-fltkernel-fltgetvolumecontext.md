---
UID: NF:fltkernel.FltGetVolumeContext
title: FltGetVolumeContext function
author: windows-driver-content
description: The FltGetVolumeContext routine retrieves a context that was set for a volume by a given minifilter driver.
old-location: ifsk\fltgetvolumecontext.htm
old-project: ifsk
ms.assetid: daa7d15f-580a-4668-9159-834e18b28c1f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, FltApiRef_e_to_o_8cec5d5c-18c3-4ffe-be18-fffcfc8d0c14.xml, FltGetVolumeContext, FltGetVolumeContext routine [Installable File System Drivers], G, V, e, fltkernel/FltGetVolumeContext, ifsk.fltgetvolumecontext, l, m, n, o, t, u, x"
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
-	FltGetVolumeContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetVolumeContext function


## -description


The <b>FltGetVolumeContext</b> routine retrieves a context that was set for a volume by a given minifilter driver. 


## -syntax


````
NTSTATUS FltGetVolumeContext(
  _In_  PFLT_FILTER  Filter,
  _In_  PFLT_VOLUME  Volume,
  _Out_ PFLT_CONTEXT *Context
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param Volume [in]

Opaque pointer for the volume whose context is being retrieved. This parameter is required and cannot be <b>NULL</b>. 


### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the requested context. 


## -returns



<b>FltGetVolumeContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

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
</table>
 




## -remarks



<b>FltGetVolumeContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. Thus every successful call to <b>FltGetVolumeContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for a volume, call <a href="..\fltkernel\nf-fltkernel-fltsetvolumecontext.md">FltSetVolumeContext</a>. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To delete a volume context, call <a href="..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md">FltDeleteVolumeContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsetvolumecontext.md">FltSetVolumeContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md">FltDeleteVolumeContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetVolumeContext routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

