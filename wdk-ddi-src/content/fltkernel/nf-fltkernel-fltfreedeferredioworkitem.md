---
UID: NF:fltkernel.FltFreeDeferredIoWorkItem
title: FltFreeDeferredIoWorkItem function (fltkernel.h)
description: The FltFreeDeferredIoWorkItem routine frees a work item allocated by the FltAllocateDeferredIoWorkItem routine.
old-location: ifsk\fltfreedeferredioworkitem.htm
tech.root: ifsk
ms.assetid: e061c8c3-b0f9-4341-b064-91df43303f70
ms.date: 04/16/2018
keywords: ["FltFreeDeferredIoWorkItem function"]
ms.keywords: FltApiRef_e_to_o_677ca3fc-8c9e-4e3e-8ed4-00a25779913d.xml, FltFreeDeferredIoWorkItem, FltFreeDeferredIoWorkItem routine [Installable File System Drivers], fltkernel/FltFreeDeferredIoWorkItem, ifsk.fltfreedeferredioworkitem
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
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFreeDeferredIoWorkItem
 - fltkernel/FltFreeDeferredIoWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltFreeDeferredIoWorkItem
---

# FltFreeDeferredIoWorkItem function


## -description

The <b>FltFreeDeferredIoWorkItem</b> routine frees a work item allocated by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatedeferredioworkitem">FltAllocateDeferredIoWorkItem</a> routine.

## -parameters

### -param FltWorkItem 

[in]
Opaque pointer to the work item to be freed.

## -returns

None

## -remarks

<b>FltFreeDeferredIoWorkItem</b> frees an opaque FLT_DEFERRED_IO_WORKITEM structure that was allocated by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatedeferredioworkitem">FltAllocateDeferredIoWorkItem</a>. The freed memory is returned to nonpaged pool. 

The FLT_DEFERRED_IO_WORKITEM structure is opaque: that is, its members are reserved for system use.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatedeferredioworkitem">FltAllocateDeferredIoWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueuedeferredioworkitem">FltQueueDeferredIoWorkItem</a>

