---
UID: NE:wdm._IOMMU_MAP_PHYSICAL_ADDRESS_TYPE
tech.root: kernel
title: IOMMU_MAP_PHYSICAL_ADDRESS_TYPE
ms.date: 05/27/2021
targetos: Windows
description: TBD
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_MAP_PHYSICAL_ADDRESS_TYPE
 - PIOMMU_MAP_PHYSICAL_ADDRESS_TYPE
 - IOMMU_MAP_PHYSICAL_ADDRESS_TYPE
f1_keywords:
 - _IOMMU_MAP_PHYSICAL_ADDRESS_TYPE
 - wdm/_IOMMU_MAP_PHYSICAL_ADDRESS_TYPE
 - PIOMMU_MAP_PHYSICAL_ADDRESS_TYPE
 - wdm/PIOMMU_MAP_PHYSICAL_ADDRESS_TYPE
 - IOMMU_MAP_PHYSICAL_ADDRESS_TYPE
 - wdm/IOMMU_MAP_PHYSICAL_ADDRESS_TYPE
dev_langs:
 - c++
---

## -description

The **IOMMU_MAP_PHYSICAL_ADDRESS_TYPE** enum indicates the format of the physcial address described in an [**IOMMU_MAP_PHYSICAL_ADDRESS**](./ns-wdm-iommu_map_physical_address.md) structure.

## -enum-fields

### -field MapPhysicalAddressTypeMdl

The physical address to be mapped is described by a MDL.

### -field MapPhysicalAddressTypeContiguousRange

The physical address to be mapped is physically contiguous and is described by a base and size.

### -field MapPhysicalAddressTypePfn

The physical address is described by a PFN array.

### -field MapPhysicalAddressTypeMax

Invalid physical address format.

## -remarks

## -see-also

[IOMMU_MAP_PHYSICAL_ADDRESS](./ns-wdm-iommu_map_physical_address.md)

[IOMMU_MAP_LOGICAL_RANGE_EX](./nc-wdm-iommu_map_logical_range_ex.md)

[IOMMU_MAP_IDENTITY_RANGE_EX](./nc-wdm-iommu_map_identity_range_ex.md)
