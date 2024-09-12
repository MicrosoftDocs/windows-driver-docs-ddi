---
UID: NS:d3dkmddi._DXGK_NOTIFYALLOCFLAGS
tech.root: display
title: DXGK_NOTIFYALLOCFLAGS
ms.date: 08/19/2024
targetos: Windows
description: Learn more about the DXGK_NOTIFYALLOCFLAGS structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_NOTIFYALLOCFLAGS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_NOTIFYALLOCFLAGS
 - DXGK_NOTIFYALLOCFLAGS
f1_keywords:
 - _DXGK_NOTIFYALLOCFLAGS
 - d3dkmddi/_DXGK_NOTIFYALLOCFLAGS
 - DXGK_NOTIFYALLOCFLAGS
 - d3dkmddi/DXGK_NOTIFYALLOCFLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_NOTIFYALLOCFLAGS
---

## -description

The **DXGK_NOTIFYALLOCFLAGS** structure specifies flags related to allocation notifications for paging operations.

## -struct-fields

### -field Eviction

The allocation is about to be evicted.

### -field IoMmuUnmap

The allocation is about to be unmapped from the IOMMU.

### -field Reserved

Reserved for future use; set to zero.

### -field Value

Union member that allows access to all flags in the structure.

## -remarks

The **Eviction** and **IoMmuUnmap** flags can't be set together.

A kernel-mode driver (KMD) *Dxgkrnl* uses these flags to notify the kernel-mode driver (KMD) that specific actions  before an allocation is either evicted or unmapped from the IOMMU.

For more information, see [Allocation Notification](/windows-hardware/drivers/display/allocation-notification).

## -see-also

[**DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC**](ns-d3dkmddi-dxgk_buildpagingbuffer_notifyalloc.md)

[**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md)
