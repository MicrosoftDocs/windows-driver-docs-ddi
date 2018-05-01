---
UID: NF:fltkernel.FltAllocateGenericWorkItem
title: FltAllocateGenericWorkItem function
author: windows-driver-content
description: FltAllocateGenericWorkItem allocates a generic work item.
old-location: ifsk\fltallocategenericworkitem.htm
old-project: ifsk
ms.assetid: 1be555a5-9fa7-4179-8a36-803b8792db86
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltAllocateGenericWorkItem, FltAllocateGenericWorkItem function [Installable File System Drivers], FltApiRef_a_to_d_06bae00e-f41d-4cc9-8664-94e06d004458.xml, fltkernel/FltAllocateGenericWorkItem, ifsk.fltallocategenericworkitem
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltAllocateGenericWorkItem
product: Windows
targetos: Windows
req.typenames: 
---

# FltAllocateGenericWorkItem function


## -description


<b>FltAllocateGenericWorkItem</b> allocates a generic work item. 


## -parameters






## -returns



<b>FltAllocateGenericWorkItem</b> returns <b>NULL</b> if there is insufficient memory in nonpaged pool to satisfy the request. Otherwise, it returns a pointer to the allocated work item. 




## -remarks



<b>FltAllocateGenericWorkItem</b> allocates a generic work item from nonpaged pool. 

To insert this work item into a work queue, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543452">FltQueueGenericWorkItem</a>. 

To free the work item, a minifilter driver typically calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff542971">FltFreeGenericWorkItem</a> from the worker routine that was specified in <a href="https://msdn.microsoft.com/library/windows/hardware/ff543452">FltQueueGenericWorkItem</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542971">FltFreeGenericWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543452">FltQueueGenericWorkItem</a>
 

 

