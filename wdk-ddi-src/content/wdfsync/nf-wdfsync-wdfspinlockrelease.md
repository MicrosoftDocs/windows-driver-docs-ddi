---
UID: NF:wdfsync.WdfSpinLockRelease
tech.root: wdf
title: WdfSpinLockRelease
description: The WdfSpinLockAcquire method releases a specified spin lock.
ms.date: 05/05/2023
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdfsync.h
req.idl: 
req.include-header: Wdf.h
req.irql: DISPATCH_LEVEL
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
 - WdfSpinLockRelease
f1_keywords:
 - WdfSpinLockRelease
 - wdfsync/WdfSpinLockRelease
dev_langs:
 - c++
helpviewer_keywords:
 - WdfSpinLockRelease
---

## -description

The <b>WdfSpinLockRelease</b> method releases a specified spin lock.

## -parameters

### -param SpinLock

A handle to a framework spin-lock object, obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfspinlockcreate">WdfSpinLockCreate</a>.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.

The **WdfSpinLockRelease** method releases the spin lock that a driver obtained by previously calling [**WdfSpinLockAcquire**](nf-wdfsync-wdfspinlockacquire.md). **WdfSpinLockRelease** also restores the driver's IRQL to the value that it had before the driver called **WdfSpinLockAcquire**.

For more information about spin locks, see [Using Framework Locks](/windows-hardware/drivers/wdf/using-framework-locks#framework-spin-locks).

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfspinlockcreate">WdfSpinLockCreate</a>

<a href="/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfspinlockacquire">WdfSpinLockAcquire</a>

[WdfSpinlock rule (KMDF)](/windows-hardware/drivers/devtest/kmdf-wdfspinlock)

[WdfSpinLockRelease rule (KMDF)](/windows-hardware/drivers/devtest/kmdf-wdfspinlockrelease)
