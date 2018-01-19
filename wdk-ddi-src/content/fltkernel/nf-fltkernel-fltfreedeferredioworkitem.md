---
UID: NF:fltkernel.FltFreeDeferredIoWorkItem
title: FltFreeDeferredIoWorkItem function
author: windows-driver-content
description: The FltFreeDeferredIoWorkItem routine frees a work item allocated by the FltAllocateDeferredIoWorkItem routine.
old-location: ifsk\fltfreedeferredioworkitem.htm
old-project: ifsk
ms.assetid: e061c8c3-b0f9-4341-b064-91df43303f70
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltFreeDeferredIoWorkItem
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
req.alt-api: FltFreeDeferredIoWorkItem
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
req.irql: <= DISPATCH_LEVEL
req.typenames: EXpsFontRestriction
---

# FltFreeDeferredIoWorkItem function



## -description
The <b>FltFreeDeferredIoWorkItem</b> routine frees a work item allocated by the <a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a> routine. 



## -syntax

````
VOID FltFreeDeferredIoWorkItem(
  _In_ PFLT_DEFERRED_IO_WORKITEM FltWorkItem
);
````


## -parameters

### -param FltWorkItem [in]

Opaque pointer to the work item to be freed. 


## -returns
None 


## -remarks
<b>FltFreeDeferredIoWorkItem</b> frees an opaque FLT_DEFERRED_IO_WORKITEM structure that was allocated by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a>. The freed memory is returned to nonpaged pool. 

The FLT_DEFERRED_IO_WORKITEM structure is opaque: that is, its members are reserved for system use. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltqueuedeferredioworkitem.md">FltQueueDeferredIoWorkItem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFreeDeferredIoWorkItem routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

