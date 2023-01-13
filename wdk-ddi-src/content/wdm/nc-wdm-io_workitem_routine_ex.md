---
UID: NC:wdm.IO_WORKITEM_ROUTINE_EX
title: IO_WORKITEM_ROUTINE_EX (wdm.h)
description: A WorkItemEx routine performs the processing for a work item that was queued by the IoQueueWorkItemEx or IoTryQueueWorkItem routine.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_WORKITEM_ROUTINE_EX callback function"]
ms.keywords: DrvrRtns_1ce116f5-d27b-4be5-800f-51ca29221223.xml, IO_WORKITEM_ROUTINE_EX, WorkItemEx, WorkItemEx routine [Kernel-Mode Driver Architecture], kernel.workitemex, wdm/WorkItemEx
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
 - IO_WORKITEM_ROUTINE_EX
 - wdm/IO_WORKITEM_ROUTINE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_WORKITEM_ROUTINE_EX
---

## -description

A *WorkItemEx* routine performs the processing for a work item that was queued by the [IoQueueWorkItemEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitemex) or [IoTryQueueWorkItem](/previous-versions/windows/hardware/drivers/dn683917(v=vs.85)) routine.

## -parameters

### -param IoObject [in]

Pointer to the caller's driver object or to one of the caller's device objects. This is the pointer that was passed as the *DeviceObject* parameter to [IoAllocateWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem) when the work item was allocated, or as the *IoObject* parameter to [IoInitializeWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem) or [IoTryQueueWorkItem](/previous-versions/windows/hardware/drivers/dn683917(v=vs.85)) when the work item was initialized.

### -param Context [in, optional]

Specifies driver-specific context information. This is the value that was passed as the *Context* parameter to [IoQueueWorkItemEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitemex) or [IoTryQueueWorkItem](/previous-versions/windows/hardware/drivers/dn683917(v=vs.85)) when the work item was queued.

### -param IoWorkItem [in]

Pointer to the [IO_WORKITEM](/windows-hardware/drivers/kernel/eprocess) structure for the work item. This is the pointer that was passed as the *IoWorkItem* parameter to [IoQueueWorkItemEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitemex) or [IoTryQueueWorkItem](/previous-versions/windows/hardware/drivers/dn683917(v=vs.85)).

## -remarks

Drivers can implement *WorkItemEx* routines only on Windows Vista and later versions of Windows.

The driver queues a *WorkItemEx* routine by calling [IoQueueWorkItemEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitemex) or [IoTryQueueWorkItem](/previous-versions/windows/hardware/drivers/dn683917(v=vs.85)), and a system worker thread subsequently executes the routine. For more information, see [System Worker Threads](/windows-hardware/drivers/kernel/system-worker-threads).

A *WorkItemEx* routine must run for a limited amount of time; otherwise, the system can deadlock. For more information, see [System Worker Threads](/windows-hardware/drivers/kernel/system-worker-threads).

A *WorkItemEx* routine runs at IRQL = PASSIVE_LEVEL and in a system thread context.

### Examples

To define a *WorkItemEx* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *WorkItemEx* callback routine that is named `MyWorkItemEx`, use the IO_WORKITEM_ROUTINE_EX type as shown in this code example:

```cpp
IO_WORKITEM_ROUTINE_EX MyWorkItemEx;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyWorkItemEx(
    PVOID  IoObject,
    PVOID  Context,
    PIO_WORKITEM  IoWorkItem 
    )
  {
      // Function body
  }
```

The IO_WORKITEM_ROUTINE_EX function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_WORKITEM_ROUTINE_EX function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[IO_WORKITEM](/windows-hardware/drivers/kernel/eprocess)

[IoInitializeWorkItem](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem)

[IoQueueWorkItemEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitemex)

[IoTryQueueWorkItem](/previous-versions/windows/hardware/drivers/dn683917(v=vs.85))
