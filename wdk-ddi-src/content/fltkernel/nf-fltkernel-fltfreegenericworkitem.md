---
UID: NF:fltkernel.FltFreeGenericWorkItem
title: FltFreeGenericWorkItem function (fltkernel.h)
description: The FltFreeGenericWorkItem routine frees a work item allocated by the FltAllocateGenericWorkItem routine.
old-location: ifsk\fltfreegenericworkitem.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltFreeGenericWorkItem function"]
ms.keywords: FltApiRef_e_to_o_e8a6dadd-879e-4476-9433-40a065066445.xml, FltFreeGenericWorkItem, FltFreeGenericWorkItem routine [Installable File System Drivers], fltkernel/FltFreeGenericWorkItem, ifsk.fltfreegenericworkitem
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFreeGenericWorkItem
 - fltkernel/FltFreeGenericWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltFreeGenericWorkItem
---

# FltFreeGenericWorkItem function


## -description

The <b>FltFreeGenericWorkItem</b> routine frees a work item allocated by the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocategenericworkitem">FltAllocateGenericWorkItem</a> routine.

## -parameters

### -param FltWorkItem [in]


Opaque pointer to the work item to be freed.

## -returns

None

## -remarks

<b>FltFreeGenericWorkItem</b> frees an FLT_GENERIC_WORKITEM structure that was allocated by a previous call to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocategenericworkitem">FltAllocateGenericWorkItem</a>. The freed memory is returned to nonpaged pool.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocategenericworkitem">FltAllocateGenericWorkItem</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueuegenericworkitem">FltQueueGenericWorkItem</a>
