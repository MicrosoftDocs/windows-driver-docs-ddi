---
UID: NF:ntddk.ZwAllocateLocallyUniqueId
title: ZwAllocateLocallyUniqueId function (ntddk.h)
description: The ZwAllocateLocallyUniqueId routine allocates a locally unique identifier (LUID).
tech.root: kernel
ms.date: 12/07/2022
keywords: ["ZwAllocateLocallyUniqueId function"]
ms.keywords: NtAllocateLocallyUniqueId, ZwAllocateLocallyUniqueId, ZwAllocateLocallyUniqueId routine [Kernel-Mode Driver Architecture], k111_de9ec26c-4aa4-4f1b-b876-c6e27bb2a067.xml, kernel.zwallocatelocallyuniqueid, ntddk/NtAllocateLocallyUniqueId, ntddk/ZwAllocateLocallyUniqueId
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
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
 - ZwAllocateLocallyUniqueId
 - ntddk/ZwAllocateLocallyUniqueId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwAllocateLocallyUniqueId
---

## -description

The **ZwAllocateLocallyUniqueId** routine allocates a locally unique identifier ([**LUID**](../igpupvdev/ns-igpupvdev-_luid.md)).

## -parameters

### -param Luid

Pointer to a caller-allocated buffer to receive a copy of the source LUID structure. The buffer must be at least **sizeof**(*LUID*).

## -returns

**ZwAllocateLocallyUniqueId** returns STATUS_SUCCESS if the operation succeeds or the appropriate NTSTATUS value if the operation fails. If the output parameter cannot be written to, the routine returns STATUS_ACCESS_VIOLATION.

## -remarks

The allocated [LUID](../igpupvdev/ns-igpupvdev-_luid.md) is unique to the local system only, and uniqueness is guaranteed only until the system is next restarted.

If the call to the **ZwAllocateLocallyUniqueId** function occurs in user mode, you should use the name "**NtAllocateLocallyUniqueId**" instead of "**ZwAllocateLocallyUniqueId**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**LUID**](../igpupvdev/ns-igpupvdev-_luid.md)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)