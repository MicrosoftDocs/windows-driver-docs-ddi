---
UID: NF:wdm.ExQueueWorkItem
title: ExQueueWorkItem function (wdm.h)
description: ExQueueWorkItem inserts a given work item into a queue from which a system worker thread removes the item and gives control to the routine that the caller supplied to ExInitializeWorkItem.
tech.root: ifsk
ms.date: 12/12/2022
keywords: ["ExQueueWorkItem function"]
ms.keywords: ExQueueWorkItem, ExQueueWorkItem routine [Installable File System Drivers], exref_67f4ac82-4b9b-4545-8641-2d1f8b0eb9ab.xml, ifsk.exqueueworkitem, wdm/ExQueueWorkItem
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h, Fltkernel.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExQueueWorkItem
 - wdm/ExQueueWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExQueueWorkItem
---

## -description

**ExQueueWorkItem** inserts a given work item into a queue from which a system worker thread removes the item and gives control to the routine that the caller supplied to [ExInitializeWorkItem](/windows-hardware/drivers/kernel/mmcreatemdl).

> [!WARNING]
> Use this routine with extreme caution. See the **Remarks** section below.

## -parameters

### -param WorkItem [in, out]

Pointer to the work item. This work item must have been initialized by a preceding call to [ExInitializeWorkItem](/windows-hardware/drivers/kernel/mmcreatemdl).

### -param QueueType [in]

Specifies the queue into which the work item pointed to by *WorkItem* is to be inserted. *QueueType* can be either of the following:

| Value | Meaning |
|---|---|
| **CriticalWorkQueue** | Insert the *WorkItem* into the queue from which a system thread with a real-time priority attribute will process the work item. |
| **DelayedWorkQueue** | Insert the *WorkItem* into the queue from which a system thread with a variable priority attribute will process the work item. |

The *QueueType* value **HyperCriticalWorkQueue** is reserved for system use.

## -remarks

Device drivers must use [IoQueueWorkItem](./nf-wdm-ioqueueworkitem.md) instead of **ExQueueWorkItem**. Drivers should use **ExQueueWorkItem**, and the associated [ExInitializeWorkItem](/windows-hardware/drivers/kernel/mmcreatemdl), only in cases where the specified work item is not associated with a device object or device stack. In all other cases, drivers should use [IoAllocateWorkItem](./nf-wdm-ioallocateworkitem.md), [IoFreeWorkItem](./nf-wdm-iofreeworkitem.md), and **IoQueueWorkItem** because only these routines ensure that the device object associated with the specified work item remains available until the work item has been processed.

The callback routine that was specified in the *Routine* parameter to [ExInitializeWorkItem](/windows-hardware/drivers/kernel/mmcreatemdl) is called in a system context at IRQL PASSIVE_LEVEL. This caller-supplied routine is responsible for freeing the work item when it is no longer needed by calling [ExFreePool](../ntddk/nf-ntddk-exfreepool.md) or [ExFreePoolWithTag](./nf-wdm-exfreepoolwithtag.md).

System worker threads are a limited resource. Drivers must not permanently reserve a work item for the driver's use. Work items are designed for operations that complete quickly. Drivers should free any work items that they allocate as soon as possible.

A driver must not wait for its callback routine to complete an operation if it is already holding one synchronization object and might attempt to acquire another. To prevent deadlock, a driver should release any currently held semaphores, mutexes, resource variables, and so forth before it calls **ExQueueWorkItem**.

The value of *QueueType* determines the runtime priority at which the callback routine is run, as follows:

- If the callback runs in the system thread with a real-time priority attribute, the callback routine cannot be preempted except by threads with higher real-time priorities.

- If the callback runs in the system thread with a variable priority attribute, the callback can be preempted by threads with higher variable and real-time priorities, and the callback is scheduled to run round-robin with other threads of the same priority for a quantum each.

Threads at either priority remain interruptible.

## -see-also

[ExFreePool](../ntddk/nf-ntddk-exfreepool.md)

[ExFreePoolWithTag](./nf-wdm-exfreepoolwithtag.md)

[ExInitializeWorkItem](/windows-hardware/drivers/kernel/mmcreatemdl)

[IoAllocateWorkItem](./nf-wdm-ioallocateworkitem.md)

[IoFreeWorkItem](./nf-wdm-iofreeworkitem.md)

[IoQueueWorkItem](./nf-wdm-ioqueueworkitem.md)

[WORK_QUEUE_ITEM](./ns-wdm-_work_queue_item.md)