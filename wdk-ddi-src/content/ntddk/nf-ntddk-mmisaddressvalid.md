---
UID: NF:ntddk.MmIsAddressValid
title: MmIsAddressValid function (ntddk.h)
description: The MmIsAddressValid routine checks whether a page fault will occur for a read or write operation at a given virtual address.Warning  We do not recommend using this function.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["MmIsAddressValid function"]
ms.keywords: MmIsAddressValid, MmIsAddressValid routine [Kernel-Mode Driver Architecture], k106_5f0349a5-5fdb-4263-b91a-d00667729901.xml, kernel.mmisaddressvalid, ntddk/MmIsAddressValid
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmIsAddressValid
 - ntddk/MmIsAddressValid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmIsAddressValid
---

## -description

The **MmIsAddressValid** routine checks whether a page fault will occur for a read or write operation at a given virtual address.

> [!WARNING]
> We do not recommend using this function.

## -parameters

### -param VirtualAddress [in]

A pointer to the nonpaged virtual address to check. The caller must ensure that this address cannot be paged out or deleted for the duration of this call. Even after the return from the call, you must not page out or delete this address. If you do page out or delete this address, the return value might be unreliable. Paging out or deleting this address might cause the computer to stop responding (that is, *crash*).

## -returns

If no page fault would occur from reading or writing at the given virtual address, **MmIsAddressValid** returns **TRUE**.

## -remarks

Even if **MmIsAddressValid** returns **TRUE**, accessing the address can cause page faults unless the memory has been locked down or the address is a valid nonpaged pool address.

## -see-also

[MmProbeAndLockPages](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages)
