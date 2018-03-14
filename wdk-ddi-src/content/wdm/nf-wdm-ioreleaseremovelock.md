---
UID: NF:wdm.IoReleaseRemoveLock
title: IoReleaseRemoveLock macro
author: windows-driver-content
description: The IoReleaseRemoveLock routine releases a remove lock acquired with a previous call to IoAcquireRemoveLock.
old-location: kernel\ioreleaseremovelock.htm
old-project: kernel
ms.assetid: 75cf8262-8cb4-428e-b18e-b80121c6390e
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoReleaseRemoveLock, IoReleaseRemoveLock routine [Kernel-Mode Driver Architecture], k104_7ac4aba4-0219-4ad2-81bf-028ec989e1f2.xml, kernel.ioreleaseremovelock, wdm/IoReleaseRemoveLock
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
req.ddi-compliance: RemoveLock, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockMnRemove, RemoveLockMnRemove2, RemoveLockMnSurpriseRemove, RemoveLockQueryMnRemove, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePnp, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoReleaseRemoveLock
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoReleaseRemoveLock macro


## -description


The <b>IoReleaseRemoveLock</b> routine releases a remove lock acquired with a previous call to <a href="..\wdm\nf-wdm-ioacquireremovelock.md">IoAcquireRemoveLock</a>.


## -syntax


````
VOID IoReleaseRemoveLock(
  _In_ PIO_REMOVE_LOCK RemoveLock,
  _In_ PVOID           Tag
);
````


## -parameters




### -param RemoveLock [in]

Pointer to an <b>IO_REMOVE_LOCK</b> structure that the caller passed to a previous call to <b>IoAcquireRemoveLock</b>. 


### -param Tag [in]

Pointer to a caller-supplied tag that was passed to a previous call to <b>IoAcquireRemoveLock</b>. 

If a driver specified a <i>Tag</i> when it acquired the lock, the driver must specify the same <i>Tag</i> when releasing the lock. If the tags do not match, this routine asserts on a checked build.

If the call to <b>IoAcquireRemoveLock</b> did not specify a <i>Tag</i>, then this parameter is <b>NULL</b>.

The I/O system only uses this parameter on checked builds. 


## -remarks



A driver calls <b>IoReleaseRemoveLock</b> when it has completed the I/O operation for which it called <a href="..\wdm\nf-wdm-ioacquireremovelock.md">IoAcquireRemoveLock</a>.

<ul>
<li>
For I/O operations (including power and PnP IRPs) that set an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine, a driver should call <b>IoReleaseRemoveLock</b> in the <i>IoCompletion</i> routine, after calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>.

</li>
<li>
For I/O operations that do not set an <i>IoCompletion</i> routine, a driver should call <b>IoReleaseRemoveLock</b> after passing the current IRP to the next-lower driver, but before exiting the dispatch routine.

</li>
</ul>
Each call to <a href="..\wdm\nf-wdm-ioacquireremovelock.md">IoAcquireRemoveLock</a> must have a corresponding call to <b>IoReleaseRemoveLock</b>. 

<b>IoReleaseRemoveLock</b> decrements the count of outstanding acquisitions of the remove lock. If the count goes to zero and the driver has received an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request, <b>IoReleaseRemoveLock</b> sets an internal event. When a driver is ready to delete a device object, it calls a similar routine, <a href="..\wdm\nf-wdm-ioreleaseremovelockandwait.md">IoReleaseRemoveLockAndWait</a>. The driver makes this call only in its dispatch code for an <b>IRP_MN_REMOVE_DEVICE</b> request. The <b>IoReleaseRemoveLockAndWait</b> routine does not return until <b>IoReleaseRemoveLock</b> sets the event that indicates the acquisition count is zero. After <b>IoReleaseRemoveLockAndWait</b> returns, the driver can safely detach and delete the device object.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565504">Using Remove Locks</a>. 




## -see-also

<a href="..\wdm\nf-wdm-ioinitializeremovelock.md">IoInitializeRemoveLock</a>



<a href="..\wdm\nf-wdm-ioreleaseremovelockandwait.md">IoReleaseRemoveLockAndWait</a>



<a href="..\wdm\nf-wdm-ioacquireremovelock.md">IoAcquireRemoveLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoReleaseRemoveLock routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

