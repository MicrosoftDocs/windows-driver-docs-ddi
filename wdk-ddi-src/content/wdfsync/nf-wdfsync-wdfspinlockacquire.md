---
UID: NF:wdfsync.WdfSpinLockAcquire
tech.root: wdf
title: WdfSpinLockAcquire
description: The WdfSpinLockAcquire method acquires a specified spin lock.
ms.date: 05/05/2023
targetos: Windows
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdfsync.h
req.idl: 
req.include-header: Wdf.h
req.irql: <=DISPATCH_LEVEL
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wdfsync.h
api_name:
 - WdfSpinLockAcquire
f1_keywords:
 - WdfSpinLockAcquire
 - wdfsync/WdfSpinLockAcquire
dev_langs:
 - c++
helpviewer_keywords:
 - WdfSpinLockAcquire
---

## -description

The <b>WdfSpinLockAcquire</b> method acquires a specified spin lock.

## -parameters

### -param SpinLock

A handle to a framework spin-lock object, obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfspinlockcreate">WdfSpinLockCreate</a>.

## -remarks

The **WdfSpinLockAcquire** method returns after the specified spin lock has been acquired. For KMDF, the method returns at IRQL = DISPATCH_LEVEL. For UMDF, the method returns at passive.
 
Your driver cannot call **WdfSpinLockAcquire** to acquire a spin lock that the driver has specified in a [**WDF_INTERRUPT_CONFIG**](../wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config.md) structure.
 
For more information about spin locks, see [Using Framework Locks](/windows-hardware/drivers/wdf/using-framework-locks).

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfspinlockcreate">WdfSpinLockCreate</a>

<a href="/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfspinlockrelease">WdfSpinLockRelease</a>

[WdfSpinlock rule (KMDF)](/windows-hardware/drivers/devtest/kmdf-wdfspinlock)

[WdfSpinLockRelease rule (KMDF)](/windows-hardware/drivers/devtest/kmdf-wdfspinlockrelease)
