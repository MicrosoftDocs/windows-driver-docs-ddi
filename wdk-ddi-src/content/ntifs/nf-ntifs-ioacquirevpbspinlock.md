---
UID: NF:ntifs.IoAcquireVpbSpinLock
title: IoAcquireVpbSpinLock function
author: windows-driver-content
description: The IoAcquireVpbSpinLock routine acquires the Volume Parameter Block (VPB) spin lock.
old-location: ifsk\ioacquirevpbspinlock.htm
old-project: ifsk
ms.assetid: 2a385a7a-e4c9-41ff-aaf2-7a4607fa2b2b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoAcquireVpbSpinLock, IoAcquireVpbSpinLock routine [Installable File System Drivers], ifsk.ioacquirevpbspinlock, ioref_b5833043-4673-46ff-850c-bd71da7defef.xml, ntifs/IoAcquireVpbSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoAcquireVpbSpinLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoAcquireVpbSpinLock function


## -description


The <b>IoAcquireVpbSpinLock</b> routine acquires the Volume Parameter Block (VPB) spin lock. 


## -syntax


````
VOID IoAcquireVpbSpinLock(
  _Out_ PKIRQL Irql
);
````


## -parameters




### -param Irql [out]

Pointer to a caller-allocated variable in which to save the current IRQL for a subsequent call to <a href="..\ntifs\nf-ntifs-ioreleasevpbspinlock.md">IoReleaseVpbSpinLock</a>. Usually the <i>Irql</i> is saved on the stack as a local variable.


## -returns



None




## -remarks



File systems call <b>IoAcquireVpbSpinLock</b> to acquire the VPB spin lock. This global spin lock must be acquired before accessing any of the following fields of a VPB: 

<ul>
<li>
Flags (specifically, VPB_MOUNTED)

</li>
<li>
DeviceObject

</li>
<li>
RealDevice

</li>
<li>
ReferenceCount

</li>
</ul>
Every successful call to <b>IoAcquireVpbSpinLock</b> must be matched by a subsequent call to <a href="..\ntifs\nf-ntifs-ioreleasevpbspinlock.md">IoReleaseVpbSpinLock</a>. To prevent deadlock, the holder of the VPB spin lock must release it immediately when it is no longer needed. 

Before using <b>IoAcquireVpbSpinLock</b> and <a href="..\ntifs\nf-ntifs-ioreleasevpbspinlock.md">IoReleaseVpbSpinLock</a>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample. 

After calling <b>IoAcquireVpbSpinLock</b>, the caller executes at IRQL DISPATCH_LEVEL. Calling <a href="..\ntifs\nf-ntifs-ioreleasevpbspinlock.md">IoReleaseVpbSpinLock</a> restores the caller's original IRQL. 




## -see-also

<a href="..\ntifs\nf-ntifs-ioreleasevpbspinlock.md">IoReleaseVpbSpinlock</a>



 

 


