---
UID: NC:wdm.IO_WORKITEM_ROUTINE
title: IO_WORKITEM_ROUTINE (wdm.h)
description: A WorkItem routine performs the processing for a work item that was queued by the IoQueueWorkItem routine.
old-location: kernel\workitem.htm
tech.root: kernel
ms.date: 04/30/2018
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

# IO_WORKITEM_ROUTINE callback function


## -description

A <i>WorkItem</i> routine performs the processing for a work item that was queued by the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a> routine.

## -parameters

### -param DeviceObject 

[in]
Pointer to one of the caller's device objects. This is the pointer that was passed as the <i>DeviceObject</i> parameter to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a> when the work item was allocated, or as the <i>IoObject</i> parameter to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a> when the work item was initialized.

### -param Context 

[in, optional]
Specifies driver-specific context information. This is the value that was passed as the <i>Context</i> parameter to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a> when the work item was queued.

## -remarks

The driver queues a <i>WorkItem</i> routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>, and a system worker thread subsequently executes the routine. A <i>WorkItem</i> routine must run for a limited amount of time; otherwise, the system can deadlock. For more information, see <a href="/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>.

A <i>WorkItem</i> routine runs at IRQL = PASSIVE_LEVEL and in a system thread context.


#### Examples

To define a <i>WorkItem</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>WorkItem</i> callback routine that is named <code>MyWorkItem</code>, use the IO_WORKITEM_ROUTINE type as shown in this code example:


```
IO_WORKITEM_ROUTINE MyWorkItem;
```

Then, implement your callback routine as follows:


```
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

The IO_WORKITEM_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_WORKITEM_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>

