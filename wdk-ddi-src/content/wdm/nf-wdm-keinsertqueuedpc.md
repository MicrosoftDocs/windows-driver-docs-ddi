---
UID: NF:wdm.KeInsertQueueDpc
title: KeInsertQueueDpc function (wdm.h)
description: The KeInsertQueueDpc routine queues a DPC for execution.
old-location: kernel\keinsertqueuedpc.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["KeInsertQueueDpc function"]
ms.keywords: KeInsertQueueDpc, KeInsertQueueDpc routine [Kernel-Mode Driver Architecture], k105_7f821e29-508f-4216-92db-a2e18c21d17c.xml, kernel.keinsertqueuedpc, wdm/KeInsertQueueDpc
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: MarkingQueuedIrps, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KeInsertQueueDpc
 - wdm/KeInsertQueueDpc
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeInsertQueueDpc
---

# KeInsertQueueDpc function

## -description

The **KeInsertQueueDpc** routine queues a DPC for execution.

## -parameters

### -param Dpc

[in, out] Pointer to the [KDPC](/windows-hardware/drivers/kernel/eprocess) structure for the DPC object. This structure must have been initialized by either [KeInitializeDpc](/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc) or [KeInitializeThreadedDpc](/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializethreadeddpc).

### -param SystemArgument1

[in, optional] Specifies driver-determined context data. This value is passed as the *SystemArgument1* parameter to the DPC object's [CustomDpc](/windows-hardware/drivers/ddi/wdm/nc-wdm-kdeferred_routine) or [CustomThreadedDpc](nc-wdm-kdeferred_routine.md) routine.

### -param SystemArgument2

[in, optional] Specifies driver-determined context data. This value is passed as the *SystemArgument2* parameter to the DPC object's [CustomDpc](/windows-hardware/drivers/ddi/wdm/nc-wdm-kdeferred_routine) or *CustomThreadedDpc* routine.

## -returns

If the specified DPC object is not currently in a DPC queue, **KeInsertQueueDpc** queues the DPC and returns **TRUE**.

## -remarks

If the specified DPC object has already been queued, no operation is performed except to return **FALSE**. Otherwise, the DPC object is inserted in a DPC queue. For more information about DPC queues, see [Organization of DPC Queues](/windows-hardware/drivers/kernel/organization-of-dpc-queues).

Note that a particular DPC object and the function that it represents can each be queued for execution only once at any particular time.

## -see-also

[CustomDpc](/windows-hardware/drivers/ddi/wdm/nc-wdm-kdeferred_routine)

[CustomThreadedDpc](nc-wdm-kdeferred_routine.md)

[KeInitializeDpc](/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc)

[KeRemoveQueueDpc](/windows-hardware/drivers/ddi/wdm/nf-wdm-keremovequeuedpc)
