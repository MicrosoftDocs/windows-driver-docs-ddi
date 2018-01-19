---
UID: NF:fltkernel.FltReferenceContext
title: FltReferenceContext function
author: windows-driver-content
description: FltReferenceContext increments the reference count on a context structure.
old-location: ifsk\fltreferencecontext.htm
old-project: ifsk
ms.assetid: 3e49f80e-3c30-4796-b2f3-7df37746d97b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltReferenceContext
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
req.alt-api: FltReferenceContext
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
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
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetinstancecontext.md">FltGetInstanceContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetstreamcontext.md">FltGetStreamContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetstreamhandlecontext.md">FltGetStreamHandleContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReferenceContext function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

