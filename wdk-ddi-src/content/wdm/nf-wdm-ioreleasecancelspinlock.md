---
UID: NF:wdm.IoReleaseCancelSpinLock
tech.root: kernel
title: IoReleaseCancelSpinLock
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the IoReleaseCancelSpinLock routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
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
 - IoReleaseCancelSpinLock
f1_keywords:
 - IoReleaseCancelSpinLock
 - wdm/IoReleaseCancelSpinLock
dev_langs:
 - c++
helpviewer_keywords:
 - IoReleaseCancelSpinLock
---

## -description

The **IoReleaseCancelSpinLock** routine releases the cancel spin lock after the driver has changed the cancelable state of an IRP.

## -parameters

### -param Irql

[in] The IRQL to be restored. The caller obtained this IRQL in the previous call to the [**IoAcquireCancelSpinLock**](nf-wdm-ioacquirecancelspinlock.md) routine.

## -remarks

This routine is a reciprocal to **IoAcquireCancelSpinLock**.

This routine also releases the cancel spin lock from the driver's [*Cancel*](nc-wdm-driver_cancel.md) routine.

The holder of the cancel spin lock runs at IRQL = DISPATCH\_LEVEL after calling **IoAcquireCancelSpinLock**. **IoReleaseCancelSpinLock** restores the original IRQL of the caller.

## -see-also

[**IoAcquireCancelSpinLock**](nf-wdm-ioacquirecancelspinlock.md)

[**IoSetCancelRoutine**](nf-wdm-iosetcancelroutine.md)
