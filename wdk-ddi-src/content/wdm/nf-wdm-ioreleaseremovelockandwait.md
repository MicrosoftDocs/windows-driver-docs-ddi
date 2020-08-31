---
UID: NF:wdm.IoReleaseRemoveLockAndWait
title: IoReleaseRemoveLockAndWait macro (wdm.h)
description: The IoReleaseRemoveLockAndWait routine releases a remove lock that the driver acquired in a previous call to IoAcquireRemoveLock, and waits until all acquisitions of the lock have been released.
old-location: kernel\ioreleaseremovelockandwait.htm
tech.root: kernel
ms.assetid: 79edb8b3-24a1-4dc0-b816-f78bbc888d3a
ms.date: 04/30/2018
keywords: ["IoReleaseRemoveLockAndWait macro"]
ms.keywords: IoReleaseRemoveLockAndWait, IoReleaseRemoveLockAndWait routine [Kernel-Mode Driver Architecture], k104_bcbaa84f-6216-4ea4-9527-fb7e62d323a3.xml, kernel.ioreleaseremovelockandwait, wdm/IoReleaseRemoveLockAndWait
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoReleaseRemoveLockAndWaitOutsideRemoveDevice, RemoveLock, RemoveLockCheck, RemoveLockMnRemove, RemoveLockMnRemove2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoReleaseRemoveLockAndWait
 - wdm/IoReleaseRemoveLockAndWait
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoReleaseRemoveLockAndWait
---

# IoReleaseRemoveLockAndWait macro


## -description

The <b>IoReleaseRemoveLockAndWait</b> routine releases a remove lock that the driver acquired in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioacquireremovelock">IoAcquireRemoveLock</a>, and waits until all acquisitions of the lock have been released.

## -parameters

### -param RemoveLock 

[in]
Pointer to an <b>IO_REMOVE_LOCK</b> structure that the caller passed in a previous call to <b>IoAcquireRemoveLock</b>.

### -param Tag 

[in]
Pointer to a caller-supplied tag that was passed in a previous call to <b>IoAcquireRemoveLock</b>. 

If a driver specified a <i>Tag</i> when it acquired the lock, the driver must specify the same <i>Tag</i> when releasing the lock. 

If the call to <b>IoAcquireRemoveLock</b> did not specify a <i>Tag</i>, then this parameter is <b>NULL</b>.

## -remarks

A driver typically calls this routine in its dispatch code for an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> request. To allow queued I/O requests to complete, each driver should call <b>IoReleaseRemoveLockAndWait</b> <i>after</i> it passes the remove IRP to the next-lower driver, and <i>before</i> it releases memory, calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodetachdevice">IoDetachDevice</a>, or calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice">IoDeleteDevice</a>. The <b>IoReleaseRemoveLockAndWait</b> routine waits for the bus driver to cancel any IRPs that might be outstanding (for example, an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-wait-wake">IRP_MN_WAIT_WAKE</a> IRP).

A driver must acquire the remove lock before calling <b>IoReleaseRemoveLockAndWait</b>. Typically, a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioacquireremovelock">IoAcquireRemoveLock</a> early in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch">DispatchPnp</a> routine, before the switch statement. As a result, the lock is acquired for each PnP operation, including the acquisition that is required before calling <b>IoReleaseRemoveLockAndWait</b> in the code that handles <b>IRP_MN_REMOVE_DEVICE</b>.

To release a lock from code other than the <b>IRP_MN_REMOVE_DEVICE</b> dispatch code, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreleaseremovelock">IoReleaseRemoveLock</a>.

After <b>IoReleaseRemoveLockAndWait</b> has been called for a particular remove lock, subsequent calls to <b>IoAcquireRemoveLock</b> for the same remove lock will fail. <b>IoReleaseRemoveLockAndWait</b> does not return until all outstanding acquisitions of the remove lock have been released.

After <b>IoReleaseRemoveLockAndWait</b> returns, the driver should consider the device to be in a state in which it is ready to be removed and cannot perform I/O operations. Therefore, the driver must not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeremovelock">IoInitializeRemoveLock</a> routine to re-initialize the remove lock. Violation of this rule while the driver is being verified by <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> will result in a bug check.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-remove-locks">Using Remove Locks</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch">DispatchPnp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-wait-wake">IRP_MN_WAIT_WAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioacquireremovelock">IoAcquireRemoveLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice">IoDeleteDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodetachdevice">IoDetachDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeremovelock">IoInitializeRemoveLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreleaseremovelock">IoReleaseRemoveLock</a>

