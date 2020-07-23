---
UID: NF:fltkernel.FltAllocateGenericWorkItem
title: FltAllocateGenericWorkItem function (fltkernel.h)
description: FltAllocateGenericWorkItem allocates a generic work item.
old-location: ifsk\fltallocategenericworkitem.htm
tech.root: ifsk
ms.assetid: 1be555a5-9fa7-4179-8a36-803b8792db86
ms.date: 04/16/2018
keywords: ["FltAllocateGenericWorkItem function"]
ms.keywords: FltAllocateGenericWorkItem, FltAllocateGenericWorkItem function [Installable File System Drivers], FltApiRef_a_to_d_06bae00e-f41d-4cc9-8664-94e06d004458.xml, fltkernel/FltAllocateGenericWorkItem, ifsk.fltallocategenericworkitem
f1_keywords:
 - "fltkernel/FltAllocateGenericWorkItem"
 - "FltAllocateGenericWorkItem"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltAllocateGenericWorkItem
targetos: Windows
req.typenames: 
---

# FltAllocateGenericWorkItem function


## -description


<b>FltAllocateGenericWorkItem</b> allocates a generic work item. 


## -returns



<b>FltAllocateGenericWorkItem</b> returns <b>NULL</b> if there is insufficient memory in nonpaged pool to satisfy the request. Otherwise, it returns a pointer to the allocated work item. 




## -remarks



<b>FltAllocateGenericWorkItem</b> allocates a generic work item from nonpaged pool. 

To insert this work item into a work queue, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueuegenericworkitem">FltQueueGenericWorkItem</a>. 

To free the work item, a minifilter driver typically calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreegenericworkitem">FltFreeGenericWorkItem</a> from the worker routine that was specified in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueuegenericworkitem">FltQueueGenericWorkItem</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreegenericworkitem">FltFreeGenericWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueuegenericworkitem">FltQueueGenericWorkItem</a>
 

 

