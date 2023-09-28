---
UID: NF:ntifs.IoAcquireVpbSpinLock
title: IoAcquireVpbSpinLock function (ntifs.h)
description: Learn more about the IoAcquireVpbSpinLock function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["IoAcquireVpbSpinLock function"]
ms.keywords: IoAcquireVpbSpinLock, IoAcquireVpbSpinLock routine [Installable File System Drivers], ifsk.ioacquirevpbspinlock, ioref_b5833043-4673-46ff-850c-bd71da7defef.xml, ntifs/IoAcquireVpbSpinLock
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoAcquireVpbSpinLock
 - ntifs/IoAcquireVpbSpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoAcquireVpbSpinLock
---

# IoAcquireVpbSpinLock function

## -description

The **IoAcquireVpbSpinLock** routine acquires the Volume Parameter Block (VPB) spin lock.

## -parameters

### -param Irql [out]

Pointer to a caller-allocated variable in which to save the current IRQL for a subsequent call to [**IoReleaseVpbSpinLock**](nf-ntifs-ioreleasevpbspinlock.md). Usually the **Irql** is saved on the stack as a local variable.

## -remarks

File systems call **IoAcquireVpbSpinLock** to acquire the VPB spin lock. This global spin lock must be acquired before accessing any of the following fields of a VPB:

* Flags (specifically, VPB_MOUNTED)

* DeviceObject

* RealDevice

* ReferenceCount

Every successful call to **IoAcquireVpbSpinLock** must be matched by a subsequent call to [**IoReleaseVpbSpinLock**](nf-ntifs-ioreleasevpbspinlock.md). To prevent deadlock, the holder of the VPB spin lock must release it immediately when it is no longer needed.

Before using **IoAcquireVpbSpinLock** and **IoReleaseVpbSpinLock**, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample.

After calling **IoAcquireVpbSpinLock**, the caller executes at IRQL DISPATCH_LEVEL. Calling **IoReleaseVpbSpinLock** restores the caller's original IRQL.

## -see-also

[**IoReleaseVpbSpinLock**](nf-ntifs-ioreleasevpbspinlock.md)
