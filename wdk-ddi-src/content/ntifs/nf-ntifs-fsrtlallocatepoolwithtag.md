---
UID: NF:ntifs.FsRtlAllocatePoolWithTag
title: FsRtlAllocatePoolWithTag macro (ntifs.h)
description: Learn more about the FsRtlAllocatePoolWithTag function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlAllocatePoolWithTag macro"]
ms.keywords: FsRtlAllocatePoolWithTag, FsRtlAllocatePoolWithTag routine [Installable File System Drivers], fsrtlref_1137174c-fe54-4575-98a6-64a569f91b96.xml, ifsk.fsrtlallocatepoolwithtag, ntifs/FsRtlAllocatePoolWithTag
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlAllocatePoolWithTag
 - ntifs/FsRtlAllocatePoolWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlAllocatePoolWithTag
---

# FsRtlAllocatePoolWithTag macro

## -description

The **FsRtlAllocatePoolWithTag** routine allocates pool memory.

## -parameters

### -param PoolType [in]

Type of pool to allocate. One of the following:

* **NonPagedPool**
* **PagedPool**
* **NonPagedPoolCacheAligned**
* **PagedPoolCacheAligned**

The **NonPagedPoolMustSucceed** and **NonPagedPoolCacheAlignedMustS** pool types are obsolete and should no longer be used.

### -param NumberOfBytes [in]

Number of bytes to allocate. This parameter is required and cannot be zero.

### -param Tag [in]

Specifies the pool tag for the allocated memory. Drivers normally specify the pool tag as a string of one to four 7-bit ASCII characters, delimited by single quotation marks (for example, 'abcd'). This parameter is required and cannot be zero.

## -remarks

If a pool allocation failure occurs, **FsRtlAllocatePoolWithTag** raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to **FsRtlAllocatePoolWithTag** in a *try-except* or *try-finally* statement.

The system associates the pool tag specified by the **Tag** parameter with the allocated buffer. Programming tools, such as the Windows Debugger (WinDbg), can display the pool tag associated with each allocated buffer. The value of the pool tag is normally displayed in reversed order. For example, if a caller passes 'Fred' as the value of the **Tag** parameter, this value would appear as 'derF' if pool is dumped or when tracking pool usage in the debugger.

For more information about memory management, see [Memory Management](/windows-hardware/drivers/kernel/managing-memory-for-drivers).

Memory that **FsRtlAllocatePoolWithTag** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).

Callers of **FsRtlAllocatePoolWithTag** must be running at IRQL <= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must specify a **NonPaged*Xxx*** **PoolType**. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

[**ExAllocatePoolWithTag**](../wdm/nf-wdm-exallocatepoolwithtag.md)

[**ExFreePool**](../ntddk/nf-ntddk-exfreepool.md)
