---
UID: NF:wdm.ExEnterCriticalRegionAndAcquireResourceExclusive
tech.root: kernel
title: ExEnterCriticalRegionAndAcquireResourceExclusive
ms.date: 10/03/2022
targetos: Windows
description: Learn more about the ExEnterCriticalRegionAndAcquireResourceExclusive routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2003 SP1
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DLLExport
api_location:
 - wdm.h
api_name:
 - ExEnterCriticalRegionAndAcquireResourceExclusive
f1_keywords:
 - ExEnterCriticalRegionAndAcquireResourceExclusive
 - wdm/ExEnterCriticalRegionAndAcquireResourceExclusive
dev_langs:
 - c++
helpviewer_keywords:
 - ExEnterCriticalRegionAndAcquireResourceExclusive
---

## -description

The **ExEnterCriticalRegionAndAcquireResourceExclusive** routine first enters a critical region, and then acquires exclusive access to the specified resource.

## -parameters

### -param Resource

[in, out] A pointer to the resource to acquire for exclusive access. This parameter points to a caller-allocated [**ERESOURCE**](/windows-hardware/drivers/kernel/introduction-to-eresource-routines) structure. The caller previously allocated this structure from nonpaged pool and initialized it by calling the [**ExInitializeResourceLite**](nf-wdm-exinitializeresourcelite.md) or [**ExReinitializeResourceLite**](nf-wdm-exreinitializeresourcelite.md) routine.

## -returns

A pointer to an opaque system structure. Drivers should ignore this return value.

## -remarks

If this routine is called when the specified resource is not immediately available for exclusive access, the calling thread is blocked until the resource is available.

While a driver thread runs in the critical region, the driver's user APCs and normal kernel APCs are not executed. Special kernel APCs are still executed. For more information about these APC types, see [Types of APCs](/windows-hardware/drivers/kernel/types-of-apcs).

By temporarily disabling normal kernel APCs, **ExEnterCriticalRegionAndAcquireResourceExclusive** prevents a passive-level calling thread from being preempted by an APC while the thread holds a shared resource that the APC might try to access.

The calling thread should stay in the critical region and hold the specified resource for no longer than is necessary. To release the specified resource and leave the critical region, call the [**ExReleaseResourceAndLeaveCriticalRegion**](nf-wdm-exreleaseresourceandleavecriticalregion.md) routine.

For more information about using an [**ERESOURCE**](/windows-hardware/drivers/kernel/introduction-to-eresource-routines) structure to synchronize exclusive access to a resource, see [Introduction to ERESOURCE Routines](/windows-hardware/drivers/kernel/introduction-to-eresource-routines). For more information about entering and leaving a critical region, see [Critical Regions and Guarded Regions](/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions).

## -see-also

[**ERESOURCE**](/windows-hardware/drivers/kernel/introduction-to-eresource-routines)

[**ExAcquireResourceExclusiveLite**](nf-wdm-exacquireresourceexclusivelite.md)

[**ExInitializeResourceLite**](nf-wdm-exinitializeresourcelite.md)

[**ExReinitializeResourceLite**](nf-wdm-exreinitializeresourcelite.md)

[**ExReleaseResourceLite**](nf-wdm-exreleaseresourcelite.md)

[**ExReleaseResourceAndLeaveCriticalRegion**](nf-wdm-exreleaseresourceandleavecriticalregion.md)

[**KeEnterCriticalRegion**](nf-wdm-keentercriticalregion.md)

[**KeLeaveCriticalRegion**](nf-wdm-keleavecriticalregion.md)
