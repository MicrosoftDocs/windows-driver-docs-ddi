---
UID: NF:wdm.MmGetSystemAddressForMdl
title: MmGetSystemAddressForMdl macro (wdm.h)
description: The MmGetSystemAddressForMdl routine is obsolete. Use MmGetSystemAddressForMdlSafe instead.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["MmGetSystemAddressForMdl macro"]
ms.keywords: MmGetSystemAddressForMdl, MmGetSystemAddressForMdl routine [Kernel-Mode Driver Architecture], k106_fc92914d-81c3-4ae9-a12d-86003d55bb4d.xml, kernel.mmgetsystemaddressformdl, wdm/MmGetSystemAddressForMdl
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Obsolete. Use MmGetSystemAddressForMdlSafe instead.
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
req.lib: 
req.dll: 
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmGetSystemAddressForMdl
 - wdm/MmGetSystemAddressForMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - MmGetSystemAddressForMdl
---

# MmGetSystemAddressForMdl macro

## -description

The MmGetSystemAddressForMdl routine is obsolete. Use [MmGetSystemAddressForMdlSafe](./nf-wdm-mmgetsystemaddressformdlsafe.md) instead.

**MmGetSystemAddressForMdl** is a macro that returns a nonpaged system-space virtual address for the buffer described by the MDL. It maps the physical pages described by a given MDL into system space, if they are not already mapped to system space.

## -parameters

### -param MDL [in]

Pointer to a buffer whose corresponding base virtual address is to be mapped.

## -syntax

```cpp
PVOID MmGetSystemAddressForMdl(
   MDL
);
```

## -remarks

**MmGetSystemAddressForMdl** returns the base system-space virtual address that maps the physical pages described by the given MDL.

Drivers of PIO devices call this routine to translate a virtual address range, described by the MDL at **Irp->MdlAddress**, for a user buffer to a system-space address range.

The MDL must describe nonpageable memory. In other words, the input MDL must describe an already locked-down user-space buffer returned by [MmProbeAndLockPages](./nf-wdm-mmprobeandlockpages.md), a locked-down buffer returned by [MmBuildMdlForNonPagedPool](./nf-wdm-mmbuildmdlfornonpagedpool.md), or system-space memory allocated from nonpaged pool, contiguous memory, or non-cached memory.

The returned base address has the same offset as the virtual address in the MDL.

Window issues a bug check if the attempt to map to system space fails. Therefore, you should use [MmGetSystemAddressForMdlSafe](./nf-wdm-mmgetsystemaddressformdlsafe.md) instead).

## -see-also

[MmBuildMdlForNonPagedPool](./nf-wdm-mmbuildmdlfornonpagedpool.md)

[MmGetSystemAddressForMdlSafe](./nf-wdm-mmgetsystemaddressformdlsafe.md)

[MmProbeAndLockPages](./nf-wdm-mmprobeandlockpages.md)