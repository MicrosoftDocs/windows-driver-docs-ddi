---
UID: NF:ntifs.PsReturnPoolQuota
title: PsReturnPoolQuota function (ntifs.h)
description: Learn more about the PsReturnPoolQuota function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["PsReturnPoolQuota function"]
ms.keywords: PsReturnPoolQuota, PsReturnPoolQuota routine [Installable File System Drivers], ifsk.psreturnpoolquota, ntifs/PsReturnPoolQuota, psref_7dc67879-8f0e-41a1-96cf-018dcf60afcd.xml
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsReturnPoolQuota
 - ntifs/PsReturnPoolQuota
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsReturnPoolQuota
---

# PsReturnPoolQuota function

## -description

The **PsReturnPoolQuota** routine returns pool quota of the specified pool type to the specified process.

## -parameters

### -param Process [in]

Pointer to the process whose quota is to be returned.

### -param PoolType [in]

Type of pool quota to return, which can be one of the following:

* **NonPagedPool**
* **PagedPool**
* **NonPagedPoolCacheAligned**
* **PagedPoolCacheAligned**

The **NonPagedPoolMustSucceed** and **NonPagedPoolCacheAlignedMustS** pool types are obsolete and should no longer be used.

### -param Amount [in]

Number of bytes to return to the pool quota for this process.

## -remarks

If the quota return would exceed the quota for the process, **PsReturnPoolQuota** raises an exception with the status value STATUS_QUOTA_EXCEEDED. Callers are responsible for handling this exception. Thus calls to **PsReturnPoolQuota** must be wrapped within a driver-supplied exception handler.

Every successful call to **PsChargePoolQuota** must be matched by a subsequent call to **PsReturnPoolQuota**.

For more information about memory management, see [Memory Management](/windows-hardware/drivers/kernel/managing-memory-for-drivers).

## -see-also

[**PsChargePoolQuota**](nf-ntifs-pschargepoolquota.md)
