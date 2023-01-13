---
UID: NC:wdm.IO_CSQ_INSERT_IRP_EX
title: IO_CSQ_INSERT_IRP_EX (wdm.h)
description: The CsqInsertIrpEx routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_CSQ_INSERT_IRP_EX callback function"]
ms.keywords: CsqInsertIrpEx, CsqInsertIrpEx routine [Kernel-Mode Driver Architecture], DrvrRtns_8914d2b4-6049-4d81-8f5f-4458b8bff2ed.xml, IO_CSQ_INSERT_IRP_EX, kernel.csqinsertirpex, wdm/CsqInsertIrpEx
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
 - IO_CSQ_INSERT_IRP_EX
 - wdm/IO_CSQ_INSERT_IRP_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_CSQ_INSERT_IRP_EX
---

## -description

The *CsqInsertIrpEx* routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue.

## -parameters

### -param Csq [in]

Pointer to the [IO_CSQ](/windows-hardware/drivers/kernel/eprocess) structure for the cancel-safe IRP queue.

### -param Irp [in]

Pointer to the IRP to insert into the IRP queue.

### -param InsertContext [in]

Pointer to driver-defined context for the insert operation.

## -returns

*CsqInsertIrpEx* returns STATUS_SUCCESS if the IRP has been successfully inserted, or the appropriate error code on failure.

## -remarks

The driver specifies the *CsqInsertIrpEx* routine for a cancel-safe IRP queue when it initializes the queue's **IO_CSQ** structure. The driver specifies the routine as the *CsqInsertIrp* parameter of [IoCsqInitializeEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex) when it initializes **IO_CSQ**. For more information, see [Cancel-Safe IRP Queues](/windows-hardware/drivers/kernel/cancel-safe-irp-queues).

The [IoCsqInsertIrpEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex) routine calls *CsqInsertIrpEx* to insert the IRP into the queue. The *InsertContext* parameter of **IoCsqInsertIrpEx** is passed as the *InsertContext* parameter of *CsqInsertIrpEx*.

### Examples

To define a *CsqInsertIrpEx* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *CsqInsertIrpEx* callback routine that is named `MyCsqInsertIrpEx`, use the IO_CSQ_INSERT_IRP_EX type as shown in this code example:

```cpp
IO_CSQ_INSERT_IRP_EX MyCsqInsertIrpEx;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
NTSTATUS
 MyCsqInsertIrpEx(
    struct _IO_CSQ  *Csq,
    PIRP  Irp,
    PVOID  InsertContext
    )
  {
      // Function body
  }
```

The IO_CSQ_INSERT_IRP_EX function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_CSQ_INSERT_IRP_EX function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[CsqAcquireLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock)

[CsqCompleteCanceledIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp)

[CsqInsertIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp)

[CsqPeekNextIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp)

[CsqReleaseLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock)

[CsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp)

[IO_CSQ](/windows-hardware/drivers/kernel/eprocess)

[IoCsqInitialize](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize)

[IoCsqInitializeEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex)

[IoCsqInsertIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp)

[IoCsqInsertIrpEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex)

[IoCsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp)

[IoCsqRemoveNextIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp)
