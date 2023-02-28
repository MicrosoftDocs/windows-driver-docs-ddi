---
UID: NC:wdm.IO_WORKITEM_ROUTINE
title: IO_WORKITEM_ROUTINE (wdm.h)
description: A WorkItem routine performs the processing for a work item that was queued by the IoQueueWorkItem routine.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_WORKITEM_ROUTINE callback function"]
ms.keywords: DrvrRtns_55d37b62-e72b-4aa3-b590-e9598ead0b46.xml, IO_WORKITEM_ROUTINE, WorkItem, WorkItem routine [Kernel-Mode Driver Architecture], kernel.workitem, wdm/WorkItem
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: Called at PASSIVE_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - IO_WORKITEM_ROUTINE
 - wdm/IO_WORKITEM_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_WORKITEM_ROUTINE
---

## -description

A *WorkItem* routine performs the processing for a work item that was queued by the [IoQueueWorkItem](./nf-wdm-ioqueueworkitem.md) routine.

## -parameters

### -param DeviceObject [in]

Pointer to one of the caller's device objects. This is the pointer that was passed as the *DeviceObject* parameter to [IoAllocateWorkItem](./nf-wdm-ioallocateworkitem.md) when the work item was allocated, or as the *IoObject* parameter to [IoInitializeWorkItem](./nf-wdm-ioinitializeworkitem.md) when the work item was initialized.

### -param Context [in, optional]

Specifies driver-specific context information. This is the value that was passed as the *Context* parameter to [IoQueueWorkItem](./nf-wdm-ioqueueworkitem.md) when the work item was queued.

## -remarks

The driver queues a *WorkItem* routine by calling [IoQueueWorkItem](./nf-wdm-ioqueueworkitem.md), and a system worker thread subsequently executes the routine. A *WorkItem* routine must run for a limited amount of time; otherwise, the system can deadlock. For more information, see [System Worker Threads](/windows-hardware/drivers/kernel/system-worker-threads).

A *WorkItem* routine runs at IRQL = PASSIVE_LEVEL and in a system thread context.

### Examples

To define a *WorkItem* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *WorkItem* callback routine that is named `MyWorkItem`, use the IO_WORKITEM_ROUTINE type as shown in this code example:

```cpp
IO_WORKITEM_ROUTINE MyWorkItem;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyWorkItem(
    PDEVICE_OBJECT  DeviceObject,
    PVOID  Context 
    )
  {
      // Function body
  }
```

The IO_WORKITEM_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_WORKITEM_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[IO_WORKITEM](/windows-hardware/drivers/kernel/eprocess)

[IoQueueWorkItem](./nf-wdm-ioqueueworkitem.md)