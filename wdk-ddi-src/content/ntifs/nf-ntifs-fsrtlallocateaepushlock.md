---
UID: NF:ntifs.FsRtlAllocateAePushLock
tech.root: ifsk
title: FsRtlAllocateAePushLock
ms.date: 09/29/2021
targetos: Windows
description: Learn more about the FsRtlAllocateAePushLock macro.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 20H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - FsRtlAllocateAePushLock
f1_keywords:
 - FsRtlAllocateAePushLock
 - ntifs/FsRtlAllocateAePushLock
dev_langs:
 - c++
---

## -description

**FsRtlAllocateAePushLock** allocates and initializes an auto-expand push lock.

## -parameters

### -param PoolType [in]

The type of pool memory to allocate for the auto-expand push lock. See [**POOL_TYPE**](../wdm/ne-wdm-_pool_type.md) for a description of the available pool memory types. You can modify the **PoolType** value by bitwise-ORing it with the POOL_RAISE_IF_ALLOCATION_FAILURE flag. This flag causes an exception to be raised if the allocation request cannot be satisfied.

### -param Tag [in]

The pool tag to use for the allocated memory. Specify the pool tag as a non-zero character literal of one to four characters delimited by single quotation marks (for example, 'Tag1'). The string is usually specified in reverse order (for example, '1gaT'). Each ASCII character in the tag must be a value in the range 0x20 (space) to 0x7E (tilde). Each allocation code path should use a unique pool tag to help debuggers and verifiers identify the code path.

## -returns

**FsRtlAllocateAePushLock** returns NULL if there is insufficient memory in the free pool to satisfy the request. Otherwise, the routine returns a pointer to the allocated and initialized auto-expand push lock.

## -remarks

**FsRtlAllocateAePushLock** is used to allocate pool memory for an auto-expand push lock. See [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) for more information about auto-expand push locks.

The system associates the pool tag with the allocated memory. Programming tools, such as *WinDbg*, can display the pool tag associated with each allocated buffer. *Gflags*, a tool included in [Debugging Tools for Windows](/windows-hardware/drivers/debugger/), turns on a system feature that requests allocation from [special pool](/windows-hardware/drivers/devtest/special-pool) for a particular pool tag. [*Poolmon*](/windows-hardware/drivers/devtest/poolmon), which is included in the WDK, tracks memory by pool tag.

The caller of **FsRtlAllocateAePushLock** must subsequently call [**FsRtlFreeAePushLock**](nf-ntifs-fsrtlfreeaepushlock.md) to free the allocated auto-expand push lock.

The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see [Standard Event Objects](/windows-hardware/drivers/kernel/standard-event-objects).

## -see-also

[**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md)

[**FsRtlFreeAePushLock**](nf-ntifs-fsrtlfreeaepushlock.md)

[**FsRtlSetupAdvancedHeaderEx2**](nf-ntifs-fsrtlsetupadvancedheaderex2.md)
