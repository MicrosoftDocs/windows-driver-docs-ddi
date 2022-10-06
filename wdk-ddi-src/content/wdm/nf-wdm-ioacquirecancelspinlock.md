---
UID: NF:wdm.IoAcquireCancelSpinLock
tech.root: kernel
title: IoAcquireCancelSpinLock
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the IoAcquireCancelSpinLock routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <=DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DLLExport
api_location:
 - wdm.h
api_name:
 - IoAcquireCancelSpinLock
f1_keywords:
 - IoAcquireCancelSpinLock
 - wdm/IoAcquireCancelSpinLock
dev_langs:
 - c++
helpviewer_keywords:
 - IoAcquireCancelSpinLock
---

## -description

The **IoAcquireCancelSpinLock** routine synchronizes cancelable-state transitions for IRPs in a multiprocessor-safe way.

## -parameters

### -param Irql

[out] Pointer to a variable in which to save the current IRQL for a subsequent call to [**IoReleaseCancelSpinLock**](nf-wdm-ioreleasecancelspinlock.md). Usually, the *Irql* is saved on the stack as a local variable.

## -remarks

A driver that uses the I/O manager-supplied device queues in the device object must be holding the cancel spin lock whenever it changes the cancelable state of an IRP with [**IoSetCancelRoutine**](nf-wdm-iosetcancelroutine.md).

A driver that manages its own IRP queue does not need to hold the cancel spin lock when calling **IoSetCancelRoutine**.

The holder of the cancel spin lock should release it promptly by calling [**IoReleaseCancelSpinLock**](nf-wdm-ioreleasecancelspinlock.md).

A driver-supplied *Cancel* routine is called with the cancel spin lock held. It must release the cancel spin lock when it has completed the IRP to be canceled.

## -see-also

[**IoReleaseCancelSpinLock**](nf-wdm-ioreleasecancelspinlock.md)

[**IoSetCancelRoutine**](nf-wdm-iosetcancelroutine.md)
