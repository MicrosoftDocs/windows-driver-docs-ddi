---
UID: NF:wdm.IoAcquireRemoveLock
title: IoAcquireRemoveLock macro (wdm.h)
description: The IoAcquireRemoveLock routine increments the count for a remove lock, indicating that the associated device object should not be detached from the device stack or deleted.
tech.root: kernel
ms.date: 12/13/2021
keywords: ["IoAcquireRemoveLock macro"]
ms.keywords: IoAcquireRemoveLock, IoAcquireRemoveLock routine [Kernel-Mode Driver Architecture], k104_3df0773a-09a7-40cd-8e32-58d89cf551b1.xml, kernel.ioacquireremovelock, wdm/IoAcquireRemoveLock
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequestStatusCheck, MarkDevicePower, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, MultRemoveLock, NsRemoveLockMnRemove, NsRemoveLockMnSurpriseRemove, NsRemoveLockQueryMnRemove, PowerDownAllocate, PowerDownFail, PowerUpFail, RemoveLock, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockMnRemove, RemoveLockMnRemove2, RemoveLockMnSurpriseRemove, RemoveLockQueryMnRemove, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePnp, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite, WmiForward
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoAcquireRemoveLock
 - wdm/IoAcquireRemoveLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoAcquireRemoveLock
---

# IoAcquireRemoveLock macro

## -description

The **IoAcquireRemoveLock** routine increments the count for a remove lock, indicating that the associated device object should not be detached from the device stack or deleted.

## -parameters

### -param RemoveLock [in]


Pointer to an **IO_REMOVE_LOCK** structure that the caller initialized with a previous call to [IoInitializeRemoveLock](nf-wdm-ioinitializeremovelock.md).

### -param Tag [in, optional]


Optionally points to a caller-supplied tag that identifies this instance of acquiring the remove lock. For example, a driver Dispatch routine typically sets this parameter to a pointer to the IRP the routine is processing.

If a driver specifies a *Tag* on a call to **IoAcquireRemoveLock**, the driver must supply the same *Tag* in the corresponding call to [IoReleaseRemoveLock](nf-wdm-ioreleaseremovelock.md).

The *Tag* does not have to be unique, but should be something meaningful during debugging.

## -remarks

The **IoAcquireRemoveLock** macro wraps and assumes the return value of **IoAcquireRemoveLock**, which returns NTSTATUS:

| Return value | Description |
|--|--|
| STATUS_SUCCESS | Indicates the call was successful. |
| STATUS_DELETE_PENDING | Error value indicating the driver has received an IRP_MN_REMOVE_DEVICE for the device and has called **IoReleaseRemoveLockandWait**. That routine is waiting for all remove locks to clear before returning control to the driver. |

If the routine returns any value besides STATUS_SUCCESS, do not start any new operations on the device.

A driver must initialize a remove lock with a call to [IoInitializeRemoveLock](nf-wdm-ioinitializeremovelock.md) before using the lock.

A driver must call [IoReleaseRemoveLock](nf-wdm-ioreleaseremovelock.md) to release the lock when it is no longer needed.

For more information, see [Using Remove Locks](/windows-hardware/drivers/kernel/using-remove-locks).

## -see-also

[IoInitializeRemoveLock](nf-wdm-ioinitializeremovelock.md)

[IoReleaseRemoveLock](nf-wdm-ioreleaseremovelock.md)

[IoReleaseRemoveLockAndWait](nf-wdm-ioreleaseremovelockandwait.md)
