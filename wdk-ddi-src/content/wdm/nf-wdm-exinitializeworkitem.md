---
UID: NF:wdm.ExInitializeWorkItem
title: ExInitializeWorkItem function (wdm.h)
description: ExInitializeWorkItem initializes a work-queue item with a caller-supplied context and callback routine to be queued for execution when a system worker thread is given control.
tech.root: ifsk
ms.date: 12/12/2022
keywords: ["ExInitializeWorkItem function"]
ms.keywords: ExInitializeWorkItem, ExInitializeWorkItem routine [Installable File System Drivers], exref_815c9796-c2e5-4362-926a-2fb509f3a1ae.xml, ifsk.exinitializeworkitem, wdm/ExInitializeWorkItem
req.header: wdm.h
req.include-header: FltKernel.h, Ntifs.h, Ntddk.h, Wdm.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - ExInitializeWorkItem
 - wdm/ExInitializeWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ExInitializeWorkItem
---

## -description

**ExInitializeWorkItem** initializes a work-queue item with a caller-supplied context and callback routine to be queued for execution when a system worker thread is given control.

> [!WARNING]
> Use this routine with extreme caution. See the **Remarks** section below.

## -parameters

### -param Item [in]

Pointer to a caller-allocated WORK_QUEUE_ITEM structure to be initialized. This structure must be allocated from nonpaged pool. The callback routine specified in the *Routine* parameter is responsible for freeing this work item when it is no longer needed by calling [ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool) or [ExFreePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepoolwithtag).

### -param Routine [in]

Pointer to a caller-defined routine that will be called to process the work item. This routine will be called in the context of a system thread at IRQL PASSIVE_LEVEL. This routine is declared as follows:

```cpp
VOID
(*PWORKER_THREAD_ROUTINE)(
    IN PVOID Parameter
    );
```

#### Parameter

Context information pointer that was passed in the *Context* parameter.

### -param Context [in]

Pointer to caller-supplied context information to be passed to the callback routine specified in the *Routine* parameter.

## -remarks

**ExInitializeWorkItem** initializes the work item with the specified callback routine and context pointer and **NULL** list pointers.

To add the work item to a system work queue, call [ExQueueWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-exqueueworkitem).

Work items are a limited resource, and drivers should only allocate them as needed. For example, do not allocate a work item in [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) for the driver's dedicated use.

**ExInitializeWorkItem** and [ExQueueWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-exqueueworkitem) can only be used in cases where the specified work item is not associated with any device object or device stack. In all other cases, drivers should use [IoAllocateWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem), [IoFreeWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeworkitem), and [IoQueueWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem), because only these routines ensure that the device object associated with the specified work item remains available until the work item has been processed.

## -see-also

[ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool)

[ExFreePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepoolwithtag)

[ExQueueWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-exqueueworkitem)

[IoAllocateWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem)

[IoFreeWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeworkitem)

[IoQueueWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem)

[**WORK_QUEUE_ITEM**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_work_queue_item)
