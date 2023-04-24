---
UID: NC:wdm.IO_CSQ_REMOVE_IRP
title: IO_CSQ_REMOVE_IRP (wdm.h)
description: The CsqRemoveIrp routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_CSQ_REMOVE_IRP callback function"]
ms.keywords: CsqRemoveIrp, CsqRemoveIrp routine [Kernel-Mode Driver Architecture], DrvrRtns_6d9086c3-65b8-4e0e-b5e9-0c4edbf513b1.xml, IO_CSQ_REMOVE_IRP, kernel.csqremoveirp, wdm/CsqRemoveIrp
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IO_CSQ_REMOVE_IRP
 - wdm/IO_CSQ_REMOVE_IRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_CSQ_REMOVE_IRP
---

## -description

The *CsqRemoveIrp* routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue.

## -parameters

### -param Csq [in]

Pointer to the [IO_CSQ](/windows-hardware/drivers/kernel/eprocess) structure for the cancel-safe IRP queue.

### -param Irp [in]

Pointer to the IRP to remove from the IRP queue.

## -remarks

The driver specifies the *CsqRemoveIrp* routine for a cancel-safe IRP queue when it initializes the queue's **IO_CSQ** structure. The driver specifies the routine as the *CsqRemoveIrp* parameter of [IoCsqInitialize](./nf-wdm-iocsqinitialize.md) or [IoCsqInitializeEx](./nf-wdm-iocsqinitializeex.md) when it initializes **IO_CSQ**. For more information, see [Cancel-Safe IRP Queues](/windows-hardware/drivers/kernel/cancel-safe-irp-queues).

The [IoCsqRemoveIrp](./nf-wdm-iocsqremoveirp.md) and [IoCsqRemoveNextIrp](./nf-wdm-iocsqremovenextirp.md) routines call the cancel-safe IRP queue's *CsqRemoveIrp* routine to remove the specified IRP from the queue. The system also uses *CsqRemoveIrp* to remove a canceled IRP from the queue.

### Examples

To define a *CsqRemoveIrp* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *CsqRemoveIrp* callback routine that is named `MyCsqRemoveIrp`, use the IO_CSQ_REMOVE_IRP type as shown in this code example:

```cpp
IO_CSQ_REMOVE_IRP MyCsqRemoveIrp;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID 
 MyCsqRemoveIrp(
    PIO_CSQ  Csq,
    PIRP  Irp
    )
  {
      // Function body
  }
```

The IO_CSQ_REMOVE_IRP function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_CSQ_REMOVE_IRP function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[CsqAcquireLock](./nc-wdm-io_csq_acquire_lock.md)

[CsqCompleteCanceledIrp](./nc-wdm-io_csq_complete_canceled_irp.md)

[CsqInsertIrp](./nc-wdm-io_csq_insert_irp.md)

[CsqInsertIrpEx](./nc-wdm-io_csq_insert_irp_ex.md)

[CsqPeekNextIrp](./nc-wdm-io_csq_peek_next_irp.md)

[CsqReleaseLock](./nc-wdm-io_csq_release_lock.md)

[IO_CSQ](/windows-hardware/drivers/kernel/eprocess)

[IoCsqInitialize](./nf-wdm-iocsqinitialize.md)

[IoCsqInitializeEx](./nf-wdm-iocsqinitializeex.md)

[IoCsqInsertIrp](./nf-wdm-iocsqinsertirp.md)

[IoCsqInsertIrpEx](./nf-wdm-iocsqinsertirpex.md)

[IoCsqRemoveIrp](./nf-wdm-iocsqremoveirp.md)

[IoCsqRemoveNextIrp](./nf-wdm-iocsqremovenextirp.md)