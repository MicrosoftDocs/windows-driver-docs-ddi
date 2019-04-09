---
UID: NF:fltkernel.FltReferenceContext
title: FltReferenceContext function (fltkernel.h)
description: FltReferenceContext increments the reference count on a context structure.
old-location: ifsk\fltreferencecontext.htm
tech.root: ifsk
ms.assetid: 3e49f80e-3c30-4796-b2f3-7df37746d97b
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_bb2ded16-77d3-4fb3-a6c6-870b0112df7a.xml, FltReferenceContext, FltReferenceContext function [Installable File System Drivers], fltkernel/FltReferenceContext, ifsk.fltreferencecontext
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltReferenceContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltReferenceContext function


## -description


<b>FltReferenceContext</b> increments the reference count on a context structure. 


## -parameters




### -param Context [in]

Pointer to the context. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None




## -remarks



A minifilter driver calls the <b>FltReferenceContext</b> routine to increment the reference count on a context structure. 

After a successful call to <b>FltReferenceContext</b>, the caller is responsible for decrementing the reference count on the context structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544629">FLT_CONTEXT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542997">FltGetContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543058">FltGetInstanceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543144">FltGetStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543189">FltGetVolumeContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>
 

 

