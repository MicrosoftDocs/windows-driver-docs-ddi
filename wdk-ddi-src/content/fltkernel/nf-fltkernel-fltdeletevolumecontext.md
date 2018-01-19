---
UID: NF:fltkernel.FltDeleteVolumeContext
title: FltDeleteVolumeContext function
author: windows-driver-content
description: FltDeleteVolumeContext removes a context that a given minifilter driver has set for a given volume and marks the context for deletion.
old-location: ifsk\fltdeletevolumecontext.htm
old-project: ifsk
ms.assetid: dfb376af-9910-4708-9248-1104dfc4bdec
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltDeleteVolumeContext
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
req.alt-api: FltDeleteVolumeContext
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: EXpsFontRestriction
---

# FltDeleteVolumeContext function



## -description
<b>FltDeleteVolumeContext</b> removes a context that a given minifilter driver has set for a given volume and marks the context for deletion. 



## -syntax

````
NTSTATUS FltDeleteVolumeContext(
  _In_      PFLT_FILTER  Filter,
  _In_      PFLT_VOLUME  Volume,
  _Out_opt_ PFLT_CONTEXT *OldContext
);
````


## -parameters

### -param Filter [in]

Opaque filter pointer for the caller. 


### -param Volume [in]

Opaque volume pointer for the volume. 


### -param OldContext [out, optional]

Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> to release this context when it is no longer needed. 


## -returns
<b>FltDeleteVolumeContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The specified <i>Volume</i> is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>No matching context was found. This is an error code. 

 


## -remarks
Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteVolumeContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteVolumeContext</b> to remove a context from a volume and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still in use by another thread). 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To get a volume context, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>. 

To set a volume context, call <a href="..\fltkernel\nf-fltkernel-fltsetvolumecontext.md">FltSetVolumeContext</a>. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetvolumecontext.md">FltSetVolumeContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeleteVolumeContext function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

