---
UID: NF:wdm.IoAcquireRemoveLock
title: IoAcquireRemoveLock macro
author: windows-driver-content
description: The IoAcquireRemoveLock routine increments the count for a remove lock, indicating that the associated device object should not be detached from the device stack or deleted.
old-location: kernel\ioacquireremovelock.htm
old-project: kernel
ms.assetid: 46398050-7f06-4d64-8b27-12e529884cb2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.ioacquireremovelock, wdm/IoAcquireRemoveLock, IoAcquireRemoveLock, k104_3df0773a-09a7-40cd-8e32-58d89cf551b1.xml, IoAcquireRemoveLock routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoAcquireRemoveLock
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoAcquireRemoveLock macro


## -description


The <b>IoAcquireRemoveLock</b> routine increments the count for a remove lock, 
   indicating that the associated device object should not be detached from the device stack or deleted.


## -syntax


````
NTSTATUS IoAcquireRemoveLock(
  _In_     PIO_REMOVE_LOCK RemoveLock,
  _In_opt_ PVOID           Tag
);
````


## -parameters




### -param RemoveLock [in]

Pointer to an <b>IO_REMOVE_LOCK</b> structure that the caller initialized with a 
      previous call to 
      <a href="..\wdm\nf-wdm-ioinitializeremovelock.md">IoInitializeRemoveLock</a>.


### -param Tag [in, optional]

Optionally points to a caller-supplied tag that identifies this instance of acquiring the remove lock. For 
       example, a driver Dispatch routine typically sets this parameter to a pointer to the IRP the routine is 
       processing.

If a driver specifies a <i>Tag</i> on a call to 
       <b>IoAcquireRemoveLock</b>, the driver must supply the same 
       <i>Tag</i> in the corresponding call to 
       <a href="..\wdm\nf-wdm-ioreleaseremovelock.md">IoReleaseRemoveLock</a>.

The <i>Tag</i> does not have to be unique, but should be something meaningful during 
       debugging.

The I/O system uses this parameter on checked builds only.


## -remarks



A driver must initialize a remove lock with a call to 
     <a href="..\wdm\nf-wdm-ioinitializeremovelock.md">IoInitializeRemoveLock</a> before using the 
     lock.

A driver must call <a href="..\wdm\nf-wdm-ioreleaseremovelock.md">IoReleaseRemoveLock</a> to 
     release the lock when it is no longer needed.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565504">Using Remove Locks</a>.




## -see-also

<a href="..\wdm\nf-wdm-ioinitializeremovelock.md">IoInitializeRemoveLock</a>



<a href="..\wdm\nf-wdm-ioreleaseremovelockandwait.md">IoReleaseRemoveLockAndWait</a>



<a href="..\wdm\nf-wdm-ioreleaseremovelock.md">IoReleaseRemoveLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAcquireRemoveLock routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

