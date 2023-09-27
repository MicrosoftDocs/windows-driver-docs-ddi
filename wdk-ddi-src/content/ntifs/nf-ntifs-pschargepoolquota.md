---
UID: NF:ntifs.PsChargePoolQuota
title: PsChargePoolQuota function (ntifs.h)
description: Learn more about the PsChargePoolQuota function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["PsChargePoolQuota function"]
ms.keywords: PsChargePoolQuota, PsChargePoolQuota routine [Installable File System Drivers], ifsk.pschargepoolquota, ntifs/PsChargePoolQuota, psref_690f1550-4753-4f39-bcf2-bdcf7b80112d.xml
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
 - PsChargePoolQuota
 - ntifs/PsChargePoolQuota
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsChargePoolQuota
---

# PsChargePoolQuota function

## -description

The **PsChargePoolQuota** routine charges pool quota of the specified pool type to the specified process.

## -parameters

### -param Process [in]

Pointer to the process whose quota is to be charged.

### -param PoolType [in]

Type of pool quota to charge, which can be one of the following:

* **NonPagedPool**
* **PagedPool**
* **NonPagedPoolCacheAligned**
* **PagedPoolCacheAligned**

The **NonPagedPoolMustSucceed** and **NonPagedPoolCacheAlignedMustS** pool types are obsolete and should no longer be used.

### -param Amount [in]

Number of bytes to charge against the pool quota for this process.

## -remarks

If insufficient quota exists for the process, quota is not charged, and **PsChargePoolQuota** raises an exception with the status value STATUS_QUOTA_EXCEEDED. Callers are responsible for handling this exception. Thus calls to **PsChargePoolQuota** must be wrapped within a driver-supplied exception handler.

Every successful call to **PsChargePoolQuota** must be matched by a subsequent call to **PsReturnPoolQuota**.

For more information about memory management, see [Memory Management](/windows-hardware/drivers/kernel/managing-memory-for-drivers).

## -see-also

[**PsReturnPoolQuota**](nf-ntifs-psreturnpoolquota.md)
