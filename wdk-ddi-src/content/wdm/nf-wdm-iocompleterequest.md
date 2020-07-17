---
UID: NF:wdm.IofCompleteRequest
title: IoCompleteRequest macro (wdm.h)
description: The IoCompleteRequest routine indicates that the caller has completed all processing for a given I/O request and is returning the given IRP to the I/O manager.
old-location: kernel\iocompleterequest.htm
tech.root: kernel
ms.assetid: 59252b09-00ee-4a39-9849-5ce840ee16a7
ms.date: 04/30/2018
keywords: ["IoCompleteRequest macro"]
ms.keywords: IoCompleteRequest, IoCompleteRequest routine [Kernel-Mode Driver Architecture], k104_79ea2b93-3ce8-46eb-990b-ca3e56d3e3a8.xml, kernel.iocompleterequest, wdm/IoCompleteRequest
f1_keywords:
 - "wdm/IoCompleteRequest"
 - "IoCompleteRequest"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequest, CompleteRequestStatusCheck, DoubleCompletion, IoAllocateComplete, IoBuildFsdComplete, IoSetCompletionExCompleteIrp, IrpProcessingComplete, MarkIrpPending, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, SpinLockSafe, WmiComplete, HwStorPortProhibitedDDIs, SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoCompleteRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCompleteRequest macro


## -description


The <b>IoCompleteRequest</b> macro indicates that the caller has completed all processing for a given I/O request and is returning the given IRP to the I/O manager.

> **IoCompleteRequest** wraps **IofCompleteRequest**.


## -parameters



### -param Irp

Pointer to the IRP to be completed.


### -param PriorityBoost

Specifies a system-defined CCHAR constant by which to increment the run-time priority of the original thread that requested the operation. This value is IO_NO_INCREMENT if the original thread requested an operation the driver could complete quickly (so the requesting thread is not compensated for its assumed wait for I/O to be completed) or if the IRP is completed with an error. Otherwise, the set of <i>PriorityBoost</i> constants are device-type-specific. See Ntddk.h or Wdm.h for these constants.


## -remarks



When a driver has finished all processing for a given IRP, it calls <b>IoCompleteRequest</b>. The I/O manager checks the IRP to determine whether any higher-level drivers have set up an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine for the IRP. If so, each <i>IoCompletion</i> routine is called, in turn, until every layered driver in the chain has completed the IRP.

When all drivers have completed a given IRP, the I/O manager returns status to the original requester of the operation. Note that a higher-level driver that sets up a driver-created IRP must supply an <i>IoCompletion</i> routine to release the IRP it created.

Never call <b>IoCompleteRequest</b> while holding a spin lock. Attempting to complete an IRP while holding a spin lock can cause deadlocks.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a>
 

 

