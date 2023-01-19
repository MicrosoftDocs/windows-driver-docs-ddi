---
UID: NC:wdm.IOMMU_MAP_IDENTITY_RANGE
title: IOMMU_MAP_IDENTITY_RANGE (wdm.h)
description: Creates an identity mapping for the provided MDL in the provided domain.
tech.root: kernel
ms.date: 01/19/2023
keywords: ["IOMMU_MAP_IDENTITY_RANGE callback function"]
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IOMMU_MAP_IDENTITY_RANGE
 - wdm/IOMMU_MAP_IDENTITY_RANGE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - IOMMU_MAP_IDENTITY_RANGE
---

## -description

Creates an identity mapping for the provided MDL in the specified domain.

## -parameters

### -param Domain [_In_]

A pointer to the handle to the domain.

### -param Permissions [_In_]

A ULONG variable that specifies the permissions for the mapping.

### -param Mdl [_In_]

A pointer to the MDL to map.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
