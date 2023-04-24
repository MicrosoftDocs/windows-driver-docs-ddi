---
UID: NS:ks.KSEVENTDATA
title: KSEVENTDATA (ks.h)
description: Kernel streaming clients send the KSEVENTDATA structure to the class driver to specify a notification method.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KSEVENTDATA structure"]
ms.keywords: "*PKSEVENTDATA, KSEVENTDATA, KSEVENTDATA structure [Streaming Media Devices], PKSEVENTDATA, PKSEVENTDATA structure pointer [Streaming Media Devices], ks-struct_e9669775-4fb9-465a-bd2b-fd02f718d7a3.xml, ks/KSEVENTDATA, ks/PKSEVENTDATA, stream.kseventdata"
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: KSEVENTDATA, *PKSEVENTDATA
f1_keywords:
 - PKSEVENTDATA
 - ks/PKSEVENTDATA
 - KSEVENTDATA
 - ks/KSEVENTDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSEVENTDATA
 - KSEVENTDATA
---

## -description

Kernel streaming clients send the KSEVENTDATA structure to the class driver to specify a notification method.

## -struct-fields

### -field NotificationType

Contains flags indicating what type of notification should be performed. The following table lists all the possible values for the NotificationType member.

| NotificationType Flag | Description |
|---|---|
| KSEVENTF_EVENT_HANDLE | Indicates that a Win32 synchronization or notification object handle is being passed. The KSEVENTDATA.EventHandle.Event element contains the handle. |
| KSEVENTF_SEMAPHORE_HANDLE | Indicates that a Win32 semaphore handle is being passed. The KSEVENTDATA.SemaphoreHandle.Semaphore element contains the handle. |
| KSEVENTF_EVENT_OBJECT | Indicates that a pointer to a kernel synchronization or notification object is being passed. The KSEVENTDATA.EventObject.Event element contains a pointer to this object. This is available only to kernel-mode clients. |
| KSEVENTF_SEMAPHORE_OBJECT | Indicates that a pointer to a kernel semaphore object is being passed. The KSEVENTDATA.SemaphoreObject.Semaphore element contains a pointer to this object. This is available only to kernel-mode clients. |
| KSEVENTF_DPC | Indicates that a pointer to a kernel DPC structure is being passed. The KSEVENTDATA.Dpc.Dpc element contains a pointer to the DPC. This is available only to kernel-mode clients. |
| KSEVENTF_WORKITEM | Indicates that a pointer to a kernel work item structure is being passed. The KSEVENTDATA.WorkItem.WorkQueueItem contains a pointer to the work item. This is available only to kernel-mode clients. |
| KSEVENTF_KSWORKITEM | Indicates that a pointer to a kernel streaming work item structure is being passed. The KSEVENTDATA.KsWorkItem.WorkQueueItem contains a pointer to the work item, and is queued to a previously registered kernel streaming work item. This is available only to kernel-mode clients. |

### -field EventHandle

Defines the **EventHandle** structure.

### -field EventHandle.Event

Contains a handle to a synchronization event when the KSEVENT_EVENT_HANDLE flag is set.

### -field EventHandle.Reserved

Reserved and set to zero.

### -field SemaphoreHandle

Defines the **SemaphoreHandle** structure.

### -field SemaphoreHandle.Semaphore

Contains a handle to a semaphore when the KSEVENT_SEMAPHORE_HANDLE flag is set.

### -field SemaphoreHandle.Reserved

Reserved and set to zero.

### -field SemaphoreHandle.Adjustment

Contains the adjustment to the semaphore when it is released.

### -field EventObject

Defines the **EventObject** structure.

### -field EventObject.Event

Defines the **PVOID** member **Event**.

### -field EventObject.Increment

Defines the **KPRIORITY** member **Increment**.

### -field EventObject.Reserved

Reserved and set to zero.

### -field SemaphoreObject

Defines the **SemaphoreObject** structure.

### -field SemaphoreObject.Semaphore

Defines the **PVOID** member **Semaphore**.

### -field SemaphoreObject.Increment

Defines the **KPRIORITY** member **Increment**.

### -field SemaphoreObject.Adjustment

Defines the **LONG** member **Adjustment**.

### -field Dpc

Defines the **Dpc** structure.

### -field Dpc.Dpc

Defines the **PKDPC** member **Dpc**.

### -field Dpc.ReferenceCount

Defines the **ULONG** member **ReferenceCount**.

### -field Dpc.Reserved

Reserved and set to zero.

### -field WorkItem

Defines the **WorkItem** structure.

### -field WorkItem.WorkQueueItem

Defines the **PWORK_QUEUE_ITEM** member **WorkQueueItem**.

### -field WorkItem.WorkQueueType

Defines the **WORK_QUEUE_TYPE** member **WorkQueueType**.

### -field WorkItem.Reserved

Reserved and set to zero.

### -field KsWorkItem

Defines the **KsWorkItem** structure.

### -field KsWorkItem.WorkQueueItem

Defines the **PWORK_QUEUE_ITEM** member **WorkQueueItem**.

### -field KsWorkItem.KsWorkerObject

Defines the **PKSWORKER** member **KsWorkerObject**.

### -field KsWorkItem.Reserved

Reserved for future use.

### -field Alignment

Defines the **Alignment** structure.

### -field Alignment.Unused

Not used.

### -field Alignment.Alignment

Reserved for internal use by AVStream. Minidrivers should not manipulate this member.

## -remarks

For more information, see [KS Events](/windows-hardware/drivers/stream/ks-events).

## -see-also

[KDPC](/windows-hardware/drivers/kernel/eprocess)

[KSEVENT](/windows-hardware/drivers/stream/ksevent-structure)

[KsIncrementCountedWorker](./nf-ks-ksincrementcountedworker.md)

[KsRegisterWorker](./nf-ks-ksregisterworker.md)

[**WORK_QUEUE_ITEM**](../wdm/ns-wdm-_work_queue_item.md)

[**WORK_QUEUE_TYPE**](../wdm/ne-wdm-_work_queue_type.md)