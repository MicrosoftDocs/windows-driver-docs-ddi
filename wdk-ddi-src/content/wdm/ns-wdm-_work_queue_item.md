---
UID: NS:wdm._WORK_QUEUE_ITEM
title: _WORK_QUEUE_ITEM (wdm.h)
description: The WORK_QUEUE_ITEM structure is used to post a work items to a system work queue.
tech.root: ifsk
ms.date: 01/18/2023
keywords: ["WORK_QUEUE_ITEM structure"]
ms.keywords: "*PWORK_QUEUE_ITEM, PWORK_QUEUE_ITEM, PWORK_QUEUE_ITEM structure pointer [Installable File System Drivers], WORK_QUEUE_ITEM, WORK_QUEUE_ITEM structure [Installable File System Drivers], _WORK_QUEUE_ITEM, ifsk.work_queue_item, othersystemstructures_52486f79-e8f4-4fb3-9b41-564bbd78f5d5.xml, wdm/PWORK_QUEUE_ITEM, wdm/WORK_QUEUE_ITEM"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: WORK_QUEUE_ITEM, *PWORK_QUEUE_ITEM
f1_keywords:
 - _WORK_QUEUE_ITEM
 - wdm/_WORK_QUEUE_ITEM
 - PWORK_QUEUE_ITEM
 - wdm/PWORK_QUEUE_ITEM
 - WORK_QUEUE_ITEM
 - wdm/WORK_QUEUE_ITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _WORK_QUEUE_ITEM
 - PWORK_QUEUE_ITEM
 - WORK_QUEUE_ITEM
---

## -description

The **WORK_QUEUE_ITEM** structure is used to post a work items to a system work queue.

> [!WARNING]
> Use this structure with extreme caution. See the following **Remarks** section.

## -struct-fields

### -field List

Doubly linked list structure. This structure is used to add the work item to the system work queue.

### -field WorkerRoutine

Pointer to a callback routine that processes this work item when the work item is dequeued. This callback routine is declared as follows:

```cpp
VOID
(*PWORKER_THREAD_ROUTINE)(
    IN PVOID Parameter
    );
```

#### Parameter

Context information pointer specified in the **Parameter** member.

### -field Parameter

Pointer to context information to be passed to the callback routine specified in the **WorkerRoutine** member.

## -remarks

To initialize a WORK_QUEUE_ITEM structure, call [ExInitializeWorkItem](/windows-hardware/drivers/kernel/mmcreatemdl).

To post the initialized work item to a system work queue, call [ExQueueWorkItem](./nf-wdm-exqueueworkitem.md).

ExInitializeWorkItem and ExQueueWorkItem can only be used in cases where the specified work item is not associated with any device object or device stack. In all other cases, drivers should use [IoAllocateWorkItem](./nf-wdm-ioallocateworkitem.md), [IoFreeWorkItem](./nf-wdm-iofreeworkitem.md), and [IoQueueWorkItem](./nf-wdm-ioqueueworkitem.md), because only these routines ensure that the device object associated with the specified work item remains available until the work item has been processed.

## -see-also

[ExInitializeWorkItem](/windows-hardware/drivers/kernel/mmcreatemdl)

[ExQueueWorkItem](./nf-wdm-exqueueworkitem.md)

[IoAllocateWorkItem](./nf-wdm-ioallocateworkitem.md)

[IoFreeWorkItem](./nf-wdm-iofreeworkitem.md)

[IoQueueWorkItem](./nf-wdm-ioqueueworkitem.md)