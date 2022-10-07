---
UID: NF:wdm.ExReleaseResourceAndLeaveCriticalRegion
tech.root: kernel
title: ExReleaseResourceAndLeaveCriticalRegion
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the ExReleaseResourceAndLeaveCriticalRegion routine.
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
 - ExReleaseResourceAndLeaveCriticalRegion
f1_keywords:
 - ExReleaseResourceAndLeaveCriticalRegion
 - wdm/ExReleaseResourceAndLeaveCriticalRegion
dev_langs:
 - c++
helpviewer_keywords:
 - ExReleaseResourceAndLeaveCriticalRegion
---

## -description

The **ExReleaseResourceAndLeaveCriticalRegion** routine first releases the specified resource, and then leaves the critical region.

## -parameters

### -param Resource

[in, out] A pointer to the resource to release. This parameter should be the same [**ERESOURCE**](/windows-hardware/drivers/kernel/introduction-to-eresource-routines) pointer that the caller supplied as a parameter in the previous call to the [**ExEnterCriticalRegionAndAcquireResourceExclusive**](nf-wdm-exentercriticalregionandacquireresourceexclusive.md) routine that acquired the resource.

## -remarks

After a driver calls the [**ExEnterCriticalRegionAndAcquireResourceExclusive**](nf-wdm-exentercriticalregionandacquireresourceexclusive.md) method to enter a critical region and acquire a resource for exclusive access, the driver must call **ExReleaseResourceAndLeaveCriticalRegion** to release the resource and exit the critical region.

For more information about using an **ERESOURCE** structure to synchronize exclusive access to a resource, see [Introduction to ERESOURCE Routines](/windows-hardware/drivers/kernel/introduction-to-eresource-routines). For more information about entering and leaving a critical region, see [Critical Regions and Guarded Regions](/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions).

## -see-also

[**ERESOURCE**](/windows-hardware/drivers/kernel/introduction-to-eresource-routines)

[**ExEnterCriticalRegionAndAcquireResourceExclusive**](nf-wdm-exentercriticalregionandacquireresourceexclusive.md)
