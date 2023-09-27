---
UID: NF:ntifs.FsRtlAllocatePoolWithQuotaTag
title: FsRtlAllocatePoolWithQuotaTag macro (ntifs.h)
description: Learn more about the FsRtlAllocatePoolWithQuotaTag function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlAllocatePoolWithQuotaTag macro"]
ms.keywords: FsRtlAllocatePoolWithQuotaTag, FsRtlAllocatePoolWithQuotaTag routine [Installable File System Drivers], fsrtlref_f4d15687-848c-4c31-8f30-48eb69498cc9.xml, ifsk.fsrtlallocatepoolwithquotatag, ntifs/FsRtlAllocatePoolWithQuotaTag
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
 - FsRtlAllocatePoolWithQuotaTag
 - ntifs/FsRtlAllocatePoolWithQuotaTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlAllocatePoolWithQuotaTag
---

# FsRtlAllocatePoolWithQuotaTag macro

## -description

The **FsRtlAllocatePoolWithQuotaTag** routine allocates pool memory, charging quota against the current process.

## -parameters

### -param PoolType [in]

Type of pool to allocate. One of the following:

* **NonPagedPool**
* **PagedPool**
* **NonPagedPoolCacheAligned**
* **PagedPoolCacheAligned**

The **NonPagedPoolMustSucceed** and **NonPagedPoolCacheAlignedMustS** pool types are obsolete and should no longer be used.

### -param NumberOfBytes [in]

Number of bytes to allocate.

### -param Tag [in]

Specifies the pool tag for the allocated memory. Drivers normally specify the pool tag as a string of one to four 7-bit ASCII characters, delimited by single quotation marks (for example, 'abcd'). This parameter is required and cannot be zero.

## -remarks

If a pool allocation failure occurs, **FsRtlAllocatePoolWithQuotaTag** raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to **FsRtlAllocatePoolWithQuotaTag** in a *try-except* or *try-finally* statement.

The system associates the pool tag specified by the **Tag** parameter with the allocated buffer. Programming tools, such as the Windows Debugger (WinDbg), can display the pool tag associated with each allocated buffer. The value of the pool tag is normally displayed in reversed order. For example, if a caller passes 'Fred' as the value of the **Tag** parameter, this value would appear as 'derF' if pool is dumped or when tracking pool usage in the debugger.

For more information about memory management, see [Memory Management](/windows-hardware/drivers/kernel/managing-memory-for-drivers).

Memory that **FsRtlAllocatePoolWithQuotaTag** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).

Callers of **FsRtlAllocatePoolWithQuotaTag** must be running at IRQL <= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must specify a **NonPaged****XxxPoolType**. Otherwise, the caller must be running at IRQL < DISPATCH_LEVEL.

## -see-also

[**ExAllocatePoolWithQuotaTag**](../wdm/nf-wdm-exallocatepoolwithquotatag.md)

[**ExFreePool**](../ntddk/nf-ntddk-exfreepool.md)

[**FsRtlAllocatePoolWithQuota**](/windows-hardware/drivers/ifs/fsrtlallocatepoolwithquota)
