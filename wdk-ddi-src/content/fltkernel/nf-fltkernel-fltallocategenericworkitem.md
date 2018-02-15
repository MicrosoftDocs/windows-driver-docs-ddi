---
UID: NF:fltkernel.FltAllocateGenericWorkItem
title: FltAllocateGenericWorkItem function
author: windows-driver-content
description: FltAllocateGenericWorkItem allocates a generic work item.
old-location: ifsk\fltallocategenericworkitem.htm
old-project: ifsk
ms.assetid: 1be555a5-9fa7-4179-8a36-803b8792db86
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fltkernel/FltAllocateGenericWorkItem, FltApiRef_a_to_d_06bae00e-f41d-4cc9-8664-94e06d004458.xml, FltAllocateGenericWorkItem function [Installable File System Drivers], FltAllocateGenericWorkItem, ifsk.fltallocategenericworkitem
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
-	FltAllocateGenericWorkItem
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAllocateGenericWorkItem function


## -description


<b>FltAllocateGenericWorkItem</b> allocates a generic work item. 


## -syntax


````
PFLT_GENERIC_WORKITEM FltAllocateGenericWorkItem(void);
````


## -parameters






## -returns



<b>FltAllocateGenericWorkItem</b> returns <b>NULL</b> if there is insufficient memory in nonpaged pool to satisfy the request. Otherwise, it returns a pointer to the allocated work item. 




## -remarks



<b>FltAllocateGenericWorkItem</b> allocates a generic work item from nonpaged pool. 

To insert this work item into a work queue, call <a href="..\fltkernel\nf-fltkernel-fltqueuegenericworkitem.md">FltQueueGenericWorkItem</a>. 

To free the work item, a minifilter driver typically calls <a href="..\fltkernel\nf-fltkernel-fltfreegenericworkitem.md">FltFreeGenericWorkItem</a> from the worker routine that was specified in <a href="..\fltkernel\nf-fltkernel-fltqueuegenericworkitem.md">FltQueueGenericWorkItem</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltqueuegenericworkitem.md">FltQueueGenericWorkItem</a>



<a href="..\fltkernel\nf-fltkernel-fltfreegenericworkitem.md">FltFreeGenericWorkItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAllocateGenericWorkItem function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

