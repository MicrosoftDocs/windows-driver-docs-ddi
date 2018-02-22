---
UID: NF:fltkernel.FltReferenceContext
title: FltReferenceContext function
author: windows-driver-content
description: FltReferenceContext increments the reference count on a context structure.
old-location: ifsk\fltreferencecontext.htm
old-project: ifsk
ms.assetid: 3e49f80e-3c30-4796-b2f3-7df37746d97b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_bb2ded16-77d3-4fb3-a6c6-870b0112df7a.xml, FltReferenceContext, FltReferenceContext function [Installable File System Drivers], fltkernel/FltReferenceContext, ifsk.fltreferencecontext
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltReferenceContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltReferenceContext function


## -description


<b>FltReferenceContext</b> increments the reference count on a context structure. 


## -syntax


````
VOID FltReferenceContext(
  _In_ PFLT_CONTEXT Context
);
````


## -parameters




### -param Context [in]

Pointer to the context. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None




## -remarks



A minifilter driver calls the <b>FltReferenceContext</b> routine to increment the reference count on a context structure. 

After a successful call to <b>FltReferenceContext</b>, the caller is responsible for decrementing the reference count on the context structure by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetstreamcontext.md">FltGetStreamContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetstreamhandlecontext.md">FltGetStreamHandleContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetinstancecontext.md">FltGetInstanceContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a>



<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReferenceContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

