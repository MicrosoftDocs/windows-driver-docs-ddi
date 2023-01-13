---
UID: NC:wdm.IO_CSQ_RELEASE_LOCK
title: IO_CSQ_RELEASE_LOCK (wdm.h)
description: The CsqReleaseLock routine is used by the system to release the lock that was acquired using CsqAcquireLock.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_CSQ_RELEASE_LOCK callback function"]
ms.keywords: CsqReleaseLock, CsqReleaseLock routine [Kernel-Mode Driver Architecture], DrvrRtns_054ce175-3354-4b0e-9578-19bab44d39ca.xml, IO_CSQ_RELEASE_LOCK, kernel.csqreleaselock, wdm/CsqReleaseLock
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
 - IO_CSQ_RELEASE_LOCK
 - wdm/IO_CSQ_RELEASE_LOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_CSQ_RELEASE_LOCK
---

## -description

The *CsqReleaseLock* routine is used by the system to release the lock that was acquired using [CsqAcquireLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock).

## -parameters

### -param Csq [in]

Pointer to the [IO_CSQ](/windows-hardware/drivers/kernel/eprocess) structure for the cancel-safe IRP queue.

### -param Irql [in]

Specifies an IRQL. This is the value stored by [CsqAcquireLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock) when the lock was acquired.

## -remarks

The driver specifies the *CsqReleaseLock* routine for a cancel-safe IRP queue when it initializes the queue's **IO_CSQ** structure. The driver specifies the routine as the *CsqReleaseLock* parameter of [IoCsqInitialize](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize) or [IoCsqInitializeEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex) when it initializes **IO_CSQ**. For more information, see [Cancel-Safe IRP Queues](/windows-hardware/drivers/kernel/cancel-safe-irp-queues).

The system calls this function to release a lock that was acquired using [CsqAcquireLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock).

If the driver uses a spin lock to implement locking for the queue, it must store the current IRQL when it acquires the lock, and provide the stored IRQL when it releases the lock. The *CsqAcquireLock* routine stores the current IRQL, and the system passes the stored value as the *Irql* parameter to *CsqReleaseLock*. Otherwise the driver can ignore the *Irql* parameter. For information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/spin-locks).

Drivers can use any locking mechanism to lock the queue, such as mutexes. For more information about mutexes, see [Mutex Objects](/windows-hardware/drivers/kernel/mutex-objects).

### Examples

To define a *CsqReleaseLock* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *CsqReleaseLock* callback routine that is named `MyCsqReleaseLock`, use the IO_CSQ_RELEASE_LOCK type as shown in this code example:

```cpp
IO_CSQ_RELEASE_LOCK MyCsqReleaseLock;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID 
 MyCsqReleaseLock(
    PIO_CSQ  Csq,
    KIRQL  Irql
    )
  {
      // Function body
  }
```

The IO_CSQ_RELEASE_LOCK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_CSQ_RELEASE_LOCK function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[CsqAcquireLock](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock)

[CsqCompleteCanceledIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp)

[CsqInsertIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp)

[CsqInsertIrpEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex)

[CsqPeekNextIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp)

[CsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp)

[IO_CSQ](/windows-hardware/drivers/kernel/eprocess)

[IoCsqInitialize](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize)

[IoCsqInitializeEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex)

[IoCsqInsertIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp)

[IoCsqInsertIrpEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex)

[IoCsqRemoveIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp)

[IoCsqRemoveNextIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp)
