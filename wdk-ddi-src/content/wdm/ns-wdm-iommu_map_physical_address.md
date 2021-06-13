---
UID: NS:wdm._IOMMU_MAP_PHYSICAL_ADDRESS
tech.root: kernel
title: IOMMU_MAP_PHYSICAL_ADDRESS
ms.date: 06/13/2021
targetos: Windows
description: The IOMMU_MAP_PHYSICAL_ADDRESS represents a physical address that is to be mapped to a logical address.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: IOMMU_MAP_PHYSICAL_ADDRESS, *PIOMMU_MAP_PHYSICAL_ADDRESS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_MAP_PHYSICAL_ADDRESS
 - PIOMMU_MAP_PHYSICAL_ADDRESS
 - IOMMU_MAP_PHYSICAL_ADDRESS
f1_keywords:
 - _IOMMU_MAP_PHYSICAL_ADDRESS
 - wdm/_IOMMU_MAP_PHYSICAL_ADDRESS
 - PIOMMU_MAP_PHYSICAL_ADDRESS
 - wdm/PIOMMU_MAP_PHYSICAL_ADDRESS
 - IOMMU_MAP_PHYSICAL_ADDRESS
 - wdm/IOMMU_MAP_PHYSICAL_ADDRESS
dev_langs:
 - c++
---

## -description

The **IOMMU_MAP_PHYSICAL_ADDRESS** represents a physical address that is to be mapped to a logical address. It is used by [*IOMMU_MAP_LOGICAL_RANGE_EX*](nc-wdm-iommu_map_logical_range_ex.md) and [*IOMMU_MAP_IDENTITY_RANGE_EX*](nc-wdm-iommu_map_identity_range_ex.md).

## -struct-fields

### -field MapType

A [**IOMMU_MAP_PHYSICAL_ADDRESS_TYPE**](ne-wdm-iommu_map_physical_address_type.md) value that indicates the format the physical address is represented in.

### -field Mdl

If MapType == *MapPhysicalAddressMdl*, provides a MDL that represents the physical address.

### -field Mdl.Mdl

The pointer to the MDL that represents the physical address.

### -field ContiguousRange

If MapType == *MapPhysicalAddressContiguousRange*, provides a contiguous physical address.

### -field ContiguousRange.Base

The base address of a contiguous physical address.

### -field ContiguousRange.Size

The size, in bytes, of a contiguous physical address.

### -field PfnArray

If MapType == *MapPhysicalAddressPfn*, provides a PFN array.

### -field PfnArray.PageFrame

The pointer to the PFN array.

### -field PfnArray.NumberOfPages

The number of PFNs in the PFN array.

## -remarks

When mapping a physical address using [*IOMMU_MAP_LOGICAL_RANGE_EX*](nc-wdm-iommu_map_logical_range_ex.md) or [*IOMMU_MAP_IDENTITY_RANGE_EX*](nc-wdm-iommu_map_identity_range_ex.md), the physical addresses represented must be 4K page aligned and 4K page length.

## -see-also

[IOMMU_MAP_LOGICAL_RANGE_EX](nc-wdm-iommu_map_logical_range_ex.md)

[IOMMU_MAP_IDENTITY_RANGE_EX](nc-wdm-iommu_map_identity_range_ex.md)

[IOMMU_MAP_PHYSICAL_ADDRESS_TYPE](ne-wdm-iommu_map_physical_address_type.md)
