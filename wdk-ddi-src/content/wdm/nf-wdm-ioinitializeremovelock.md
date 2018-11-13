---
UID: NF:wdm.IoInitializeRemoveLock
title: IoInitializeRemoveLock macro
author: windows-driver-content
description: The IoInitializeRemoveLock routine initializes a remove lock for a device object.
old-location: kernel\ioinitializeremovelock.htm
tech.root: kernel
ms.assetid: d85bab78-0e9e-4e71-a09b-40954df81c87
ms.date: 04/30/2018
ms.keywords: IoInitializeRemoveLock, IoInitializeRemoveLock routine [Kernel-Mode Driver Architecture], k104_b9b844b1-4bb4-4a52-8274-c5a3441f6267.xml, kernel.ioinitializeremovelock, wdm/IoInitializeRemoveLock
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoInitializeRemoveLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoInitializeRemoveLock macro


## -description


The <b>IoInitializeRemoveLock</b> routine initializes a remove lock for a device object.


## -parameters




### -param Lock [in]

Pointer to a caller-supplied <b>IO_REMOVE_LOCK</b> structure that this routine initializes with information about the lock, including a counter and a synchronization event. A driver writer must allocate this structure as part of the device object's device extension.

### -param Tag [in]

Specifies a tag to identify the creator of the lock. Driver writers typically use a 4-character string, specified in reverse order, like the tags used for <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>.

The I/O system uses this parameter if <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> is enabled, and on checked builds regardless of whether Driver Verifier is enabled. The caller should always supply a nonzero tag value for this parameter, for both free and checked builds.

### - param Maxmin [in]

Specifies the maximum number of minutes that this lock should be held. A value of zero means there is no limit. This value is typically used during debugging to identify a driver routine that holds the lock longer than expected.

The I/O system uses this parameter if Driver Verifier is enabled, and on checked builds regardless of whether Driver Verifier is enabled. If the lock is held for more than <i>MaxLockedMinutes</i> on a checked build, the operating system asserts.

### - param HighWater [in]

Specifies the maximum number of outstanding acquisitions allowed on the lock. Use 0 to specify no maximum. <i>HighWatermark</i> must be &lt;= 0x7FFFFFFF.

The I/O system uses this parameter if Driver Verifier is enabled, and on checked builds regardless of whether Driver Verifier is enabled. If the lock is acquired <i>HighWatermark</i> times on a checked build, the operating system asserts.



## -remarks



A driver can use a remove lock to track outstanding I/O operations on a device and to determine when the driver can delete its device object in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request.

Before calling <b>IoInitializeRemoveLock</b>, a driver should allocate an <b>IO_REMOVE_LOCK</b> structure in its <a href="https://msdn.microsoft.com/9ea59994-1112-4ae5-96a8-fa0670694b53">device extension</a>. A driver typically calls <b>IoInitializeRemoveLock</b> in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine, when the driver initializes the rest of the device extension for a device object.

After the <b>IoReleaseRemoveLockAndWait</b> routine returns, the driver should consider the device to be in a state in which it is ready to be removed and cannot perform I/O operations. Therefore, the driver must not call <b>IoInitializeRemoveLock</b> to re-initialize the remove lock. Violation of this rule while the driver is being verified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> will result in a bug check.

Because the driver stores the <b>IO_REMOVE_LOCK</b> structure in the device extension of a device object, the remove lock is deleted when the driver deletes the device extension as part of processing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565504">Using Remove Locks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548204">IoAcquireRemoveLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549324">IoInitializeRemoveLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549560">IoReleaseRemoveLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549567">IoReleaseRemoveLockAndWait</a>
 

 

