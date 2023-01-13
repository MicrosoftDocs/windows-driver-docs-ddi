---
UID: NC:wdm.IO_CSQ_COMPLETE_CANCELED_IRP
title: IO_CSQ_COMPLETE_CANCELED_IRP (wdm.h)
description: The CsqCompleteCanceledIrp routine is used by the system to signal to the driver that it can complete a canceled IRP.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_CSQ_COMPLETE_CANCELED_IRP callback function"]
ms.keywords: CsqCompleteCanceledIrp, CsqCompleteCanceledIrp routine [Kernel-Mode Driver Architecture], DrvrRtns_07239a13-c445-4f75-8765-ff5806515ecb.xml, IO_CSQ_COMPLETE_CANCELED_IRP, kernel.csqcompletecanceledirp, wdm/CsqCompleteCanceledIrp
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
 - IO_CSQ_COMPLETE_CANCELED_IRP
 - wdm/IO_CSQ_COMPLETE_CANCELED_IRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_CSQ_COMPLETE_CANCELED_IRP
---

## -description

The *CsqCompleteCanceledIrp* routine is used by the system to signal to the driver that it can complete a canceled IRP.

## -parameters

### -param Csq [in]

Pointer to the [IO_CSQ](/windows-hardware/drivers/kernel/eprocess) structure for the cancel-safe IRP queue.

### -param Irp [in]

Pointer to the IRP to be canceled.

## -remarks

The driver specifies the *CsqCompleteCanceledIrp* routine for a cancel-safe IRP queue when it initializes the queue's **IO_CSQ** structure. The driver specifies the routine as the *CsqCompleteCanceledIrp* parameter of [IoCsqInitialize](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize) or [IoCsqInitializeEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex) when it initializes **IO_CSQ**. For more information, see [Cancel-Safe IRP Queues](/windows-hardware/drivers/kernel/cancel-safe-irp-queues).

The system calls this routine to complete a canceled IRP that has been removed from the driver's queue. Normally, drivers just call [IoCompleteRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest) for the IRP with a status of STATUS_CANCELLED.

Drivers are not required to remove the IRP from the queue before completing it as canceled: the system always calls the queue's [CsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp) routine to remove the IRP from the queue before calling *CsqCompleteCanceledIrp*.

### Examples

To define a *CsqCompleteCanceledIrp* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *CsqCompleteCanceledIrp* callback routine that is named `MyCsqCompleteCanceledIrp`, use the IO_CSQ_COMPLETE_CANCELED_IRP type as shown in this code example:

```cpp
IO_CSQ_COMPLETE_CANCELED_IRP MyCsqCompleteCanceledIrp;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID 
 MyCsqCompleteCanceledIrp(
    _In_ PIO_CSQ  Csq,
    _In_ PIRP  Irp
    )
  {
      // Function body
  }
```

The IO_CSQ_COMPLETE_CANCELED_IRP function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_CSQ_COMPLETE_CANCELED_IRP function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[CsqCompleteCanceledIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp)

[CsqInsertIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp)

[CsqInsertIrpEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex)

[CsqPeekNextIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp)

[CsqReleaseLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock)

[CsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp)

[IO_CSQ](/windows-hardware/drivers/kernel/eprocess)

[IoCompleteRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest)

[IoCsqInitialize](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize)

[IoCsqInitializeEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex)

[IoCsqInsertIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp)

[IoCsqInsertIrpEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex)

[IoCsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp)

[IoCsqRemoveNextIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp)
