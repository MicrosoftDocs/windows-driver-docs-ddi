---
UID: NF:wdm.MmLockPagableCodeSection
title: MmLockPagableCodeSection macro (wdm.h)
description: The MmLockPagableCodeSection routine locks a section of driver code, containing a set of driver routines marked with a special compiler directive, into system space.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["MmLockPagableCodeSection macro"]
ms.keywords: MmLockPagableCodeSection, MmLockPagableCodeSection routine [Kernel-Mode Driver Architecture], k106_734069f7-1412-48d9-bae4-106391273a38.xml, kernel.mmlockpagablecodesection, wdm/MmLockPagableCodeSection
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmLockPagableCodeSection
 - wdm/MmLockPagableCodeSection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmLockPagableCodeSection
---

## -description

The **MmLockPagableCodeSection** routine locks a section of driver code, containing a set of driver routines marked with a special compiler directive, into system space.

## -parameters

### -param Address [in]

Specifies a symbolic address. This address is typically the name of a driver function within a section of driver code that has been marked with something like **#pragma alloc_text (PAGExxxx, driverfunction)**. All functions in the **PAGExxxx** section are then guaranteed to be locked down when this function returns.

## -remarks

**MmLockPagableCodeSection** returns an opaque value that the operating system uses to identify this section of the driver code. This opaque value can be passed subsequently to [**MmLockPagableSectionByHandle**](../ntddk/nf-ntddk-mmlockpagablesectionbyhandle.md) (if the driver unlocks and then later relocks the section) or to [**MmUnlockPagableImageSection**](nf-wdm-mmunlockpagableimagesection.md).

The **MmLockPagableCodeSection** routine and **MmUnlockPagableImageSection** (the routine that performs the opposite action) support drivers that can do the following:

- Defer loading a subset of driver routines into resident memory until incoming I/O requests for the driver's devices make it necessary for these routines to process IRPs.

- Make the same subset of driver routines available for paging out when they have completed the processing of I/O requests and no additional requests for the driver's devices are currently expected.

**MmLockPagableCodeSection**, **MmLockPagableSectionByHandle** and **MmUnlockPagableImageSection** are intended for use by device and intermediate drivers that have the following characteristics:

- The driver has code paths that might not be needed while the system is running, but, if they are needed, the driver's code must be resident because it runs in an arbitrary thread context or at IRQL >= DISPATCH_LEVEL.

- The driver can determine exactly when the pageable routines should be loaded and when they can be paged out again.

For example, the system-supplied fault-tolerant disk driver supports the creation of mirror sets, stripe sets, and volume sets. Yet, a particular machine can be configured only with a mirror set, only with a stripe set, only with a volume set, or with any combination of these three possible options. In these circumstances, the system ftdisk driver reduces the size of its loaded image by marking routines that explicitly support mirror, stripe, and volume sets as belonging to pageable code sections. During driver initialization, pageable code sections are made resident only if the user has configured the disks to have mirror, stripe, or volume sets. If the user repartitions the disks dynamically, the ftdisk driver locks down any additional pageable code sections necessary to support any mirror, stripe, or volume sets that the user requests.

As other examples, the system-supplied serial and parallel drivers have *DispatchCreate* and *DispatchClose* routines that are called when a particular port is opened for exclusive I/O and when the handle for an opened port is released, respectively. Yet, serial and parallel I/O requests are sporadic, determined by which applications the end user is currently running and which application options the end user is currently exercising. In these circumstances, the system serial and parallel drivers reduce the sizes of their loaded images by marking many routines as belonging to a pageable code section that the *DispatchCreate* routine makes resident only when the first port is opened for I/O.

Note that each of the preceding system drivers satisfies both criteria for having pageable sections: the driver has code paths that might not be needed while the system is running, and the driver can determine exactly when its pageable section should be loaded and can be paged out again.

Because it is an expensive operation to lock down a section, if a driver locks down a pageable code section in more than one place, use **MmLockPagableCodeSection** for the first request. Make subsequent lock requests by calling **MmLockPagableSectionByHandle** passing the handle returned by **MmLockPagableCodeSection**. Locking by handle significantly improves driver performance because the memory manager uses the opaque return value to quickly locate the relevant section rather than searching a loaded module list. A locked down section is unlocked by calling **MmUnlockPagableImageSection**.

Each driver routine within a pageable code section must be marked with the following compiler directive:

```cpp
#pragma alloc_text(PAGExxxx, DriverRoutine)
```

where *xxxx* is an optional four-character, unique identifier for the caller's pageable section and *DriverRoutine* is an entry point to be included within the pageable code section. The keyword **PAGE** and the driver-determined suffix, which can be up to four characters, are case-sensitive; that is, **PAGE** must be capitalized.

A single call to **MmLockPagableCodeSection** in, for example, a driver's *DispatchCreate* routine, causes the entire section, containing every driver routine marked with the same **PAGE***xxxx* identifier, to be locked in system space.

Certain types of driver routines cannot be made part of any driver's pageable section, including the following:

- Never make an ISR pageable. It is possible for a device driver to receive a spurious interrupt even if its device is not in use, particularly if the interrupt vector could be shared. In general, even if a driver can explicitly disable interrupts on its device, an ISR should not be made pageable.

- Never make a DPC routine pageable if the driver cannot control when the DPC is queued, such as any *DpcForIsr* or *CustomDpc* routine that might be queued from an ISR. In general, driver routines that run at IRQL >= DISPATCH_LEVEL and that can be called in an arbitrary thread context or in response to a random external event should not be made pageable.

- Never make the *DispatchRead* or *DispatchWrite* routine pageable in any driver that might be part of the system paging I/O path. The driver of a disk that might contain the system page file must have *DispatchRead* and *DispatchWrite* routines that are resident while the system is running, as must all drivers layered above such a disk driver.

Note that routines in a pageable section marked with the compiler directive **#pragma alloc_text(PAGExxxx, ...)** differ from routines marked with the compiler directive **#pragma alloc_text(INIT, ...)**. The routines in the **INIT** section are not pageable and are discarded as soon as the driver returns from its **DriverEntry** or its *Reinitialize* routine, if it has one.

The memory manager maintains an internal lock count on any driver's pageable section. Calls to **MmLockPagableCodeSection** increment this count and the reciprocal **MmUnlockPagableImageSection** decrements the count. A driver's pageable section is not available to be paged out unless this count is zero.

For more information about creating pageable code sections, see [Making Drivers Pageable](/windows-hardware/drivers/kernel/making-drivers-pageable).

## -see-also

[MmLockPagableDataSection](./nf-wdm-mmlockpagabledatasection.md)

[MmLockPagableSectionByHandle](../ntddk/nf-ntddk-mmlockpagablesectionbyhandle.md)

[MmPageEntireDriver](./nf-wdm-mmpageentiredriver.md)

[MmResetDriverPaging](./nf-wdm-mmresetdriverpaging.md)

[MmUnlockPagableImageSection](./nf-wdm-mmunlockpagableimagesection.md)