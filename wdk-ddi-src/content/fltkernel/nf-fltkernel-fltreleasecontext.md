---
UID: NF:fltkernel.FltReleaseContext
title: FltReleaseContext function
author: windows-driver-content
description: FltReleaseContext decrements the reference count on a context.
old-location: ifsk\fltreleasecontext.htm
tech.root: ifsk
ms.assetid: b0585443-b8e9-41bc-81af-5707fda2465d
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_p_to_z_1040d19b-2ecb-4229-adda-b73f5c2bc828.xml, FltReleaseContext, FltReleaseContext function [Installable File System Drivers], fltkernel/FltReleaseContext, ifsk.fltreleasecontext
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltReleaseContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltReleaseContext function


## -description


<b>FltReleaseContext</b> decrements the reference count on a context. 


## -parameters




### -param Context [in]

Pointer to the context. Must be a valid pointer to a context object for a volume, instance, stream, or stream handle. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



A minifilter driver calls <b>FltReleaseContext</b> to release a context. <b>FltReleaseContext</b> decrements the reference count on the given context. When the reference count reaches zero, the context is freed immediately if the caller is running at IRQL &lt;= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context. 

<div class="alert"><b>Note</b>    After <b>FltReleaseContext</b> returns, the caller must not use the context, because the context might have already been freed. </div>
<div> </div>
Every successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>, <b>FltGet</b><i>Xxx</i><b>Context</b>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff544291">FltReferenceContext</a> must eventually be matched by a call to <b>FltReleaseContext</b>. 

Note that the <i>OldContext</i> pointer returned by <b>FltSet</b><i>Xxx</i><b>Context</b> and the <i>Context</i> parameter that is used to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a> must also be released by calling <b>FltReleaseContext</b> when they are no longer needed. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To increment the reference count on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544291">FltReferenceContext</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>. 

Callers of <b>FltReleaseContext</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the context was allocated from nonpaged pool. If the context was allocated from paged pool, callers must be running at IRQL &lt;= APC_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542997">FltGetContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543025">FltGetFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543058">FltGetInstanceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543144">FltGetStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543175">FltGetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543189">FltGetVolumeContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544291">FltReferenceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544317">FltReleaseContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544521">FltSetInstanceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544554">FltSetTransactionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544557">FltSetVolumeContext</a>
 

 

