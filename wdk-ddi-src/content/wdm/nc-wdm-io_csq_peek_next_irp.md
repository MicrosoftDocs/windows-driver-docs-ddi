---
UID: NC:wdm.IO_CSQ_PEEK_NEXT_IRP
title: IO_CSQ_PEEK_NEXT_IRP (wdm.h)
description: The CsqPeekNextIrp routine is used by the system to find the next matching IRP in a driver-implemented, cancel-safe IRP queue.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_CSQ_PEEK_NEXT_IRP callback function"]
ms.keywords: CsqPeekNextIrp, CsqPeekNextIrp routine [Kernel-Mode Driver Architecture], DrvrRtns_83ba77b2-17fa-4fdc-bfaf-c41289f54da9.xml, IO_CSQ_PEEK_NEXT_IRP, kernel.csqpeeknextirp, wdm/CsqPeekNextIrp
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
 - IO_CSQ_PEEK_NEXT_IRP
 - wdm/IO_CSQ_PEEK_NEXT_IRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_CSQ_PEEK_NEXT_IRP
---

## -description

The *CsqPeekNextIrp* routine is used by the system to find the next matching IRP in a driver-implemented, cancel-safe IRP queue.

## -parameters

### -param Csq [in]

Pointer to the [IO_CSQ](/windows-hardware/drivers/kernel/eprocess) structure for the cancel-safe IRP queue.

### -param Irp [in, optional]

Pointer to an IRP in the driver's IRP queue, or **NULL** to specify the beginning of the queue.

### -param PeekContext [in, optional]

Pointer to driver-defined context information. The *CsqPeekNextIrp* routine returns the first IRP that follows *Irp* and matches *PeekContext*.

## -returns

*CsqPeekNextIrp* returns the first IRP that follows *Irp* in the queue and matches *PeekContext*, or **NULL** if there is no matching IRP. If *Irp* is **NULL**, *CsqPeekNextIrp* returns the first matching IRP in the queue, or **NULL** if there is no matching IRP.

## -remarks

The driver specifies the *CsqPeekNextIrp* routine for a cancel-safe IRP queue when it initializes the queue's **IO_CSQ** structure. The driver specifies the routine as the *CsqPeekNextIrp* parameter of [IoCsqInitialize](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize) or [IoCsqInitializeEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex) when it initializes **IO_CSQ**. For more information, see [Cancel-Safe IRP Queues](/windows-hardware/drivers/kernel/cancel-safe-irp-queues).

The system uses *CsqPeekNextIrp* to iterate through the IRPs in the driver's IRP queue. For example, the [IoCsqRemoveNextIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp) routine uses this routine to find the IRP to be removed.

### Examples

To define a *CsqPeekNextIrp* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *CsqPeekNextIrp* callback routine that is named `MyCsqPeekNextIrp`, use the IO_CSQ_PEEK_NEXT_IRP type as shown in this code example:

```cpp
IO_CSQ_PEEK_NEXT_IRP MyCsqPeekNextIrp;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
PIRP 
 MyCsqPeekNextIrp(
    PIO_CSQ  Csq,
    PIRP  Irp,
    PVOID  PeekContext
    )
  {
      // Function body
  }
```

The IO_CSQ_PEEK_NEXT_IRP function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_CSQ_PEEK_NEXT_IRP function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[CsqAcquireLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock)

[CsqCompleteCanceledIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp)

[CsqInsertIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp)

[CsqInsertIrpEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex)

[CsqReleaseLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock)

[CsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp)

[IO_CSQ](/windows-hardware/drivers/kernel/eprocess)

[IoCsqInitialize](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize)

[IoCsqInitializeEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex)

[IoCsqInsertIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp)

[IoCsqInsertIrpEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex)

[IoCsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp)

[IoCsqRemoveNextIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp)
