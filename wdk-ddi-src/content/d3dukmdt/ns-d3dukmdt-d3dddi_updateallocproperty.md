---
UID: NS:d3dukmdt.D3DDDI_UPDATEALLOCPROPERTY
title: D3DDDI_UPDATEALLOCPROPERTY (d3dukmdt.h)
description: Learn more about the D3DDDI_UPDATEALLOCPROPERTY structure.
tech.root: display
ms.date: 10/04/2023
keywords: ["D3DDDI_UPDATEALLOCPROPERTY structure"]
ms.keywords: D3DDDI_UPDATEALLOCPROPERTY, D3DDDI_UPDATEALLOCPROPERTY structure [Display Devices], d3dukmdt/D3DDDI_UPDATEALLOCPROPERTY, display.d3dddi_updateallocproperty
req.header: d3dukmdt.h
req.construct-type: structure
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: D3DDDI_UPDATEALLOCPROPERTY
f1_keywords:
 - D3DDDI_UPDATEALLOCPROPERTY
 - d3dukmdt/D3DDDI_UPDATEALLOCPROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDI_UPDATEALLOCPROPERTY
---

# D3DDDI_UPDATEALLOCPROPERTY structure (d3dukmdt.h)



## -description

The **D3DDDI_UPDATEALLOCPROPERTY** structure is used to update properties of a memory allocation.

## -struct-fields

### -field hPagingQueue

[in] A Handle to the paging queue used to synchronize paging operations for this call.

### -field hAllocation

[in] A handle to the allocation that will be updated.

### -field SupportedSegmentSet

[in] An index for the new supported segment set. If the current supported segment set is the same, then this will be ignored.

### -field PreferredSegment

[in] An index for the new preferred segment set. If the current preferred segment set is the same, then this will be ignored.

### -field Flags

[in] The flags that will be used to update the allocation.

### -field PagingFenceValue

[out] The paging fence value that will be synchronized with before using the new allocation. Applies to the monitored fence synchronization object associated with hPagingQueue.

### -field SetAccessedPhysically

[in] When set, the driver will update the [**AccessedPhysically**](ns-d3dukmdt-d3dddi_updateallocproperty_flags.md) property of the allocation.

[in] Specifies whether the allocation is accessed by its physical address.

### -field SetSupportedSegmentSet

[in] Specifies whether the supported segment is set to a new value.

### -field SetPreferredSegment

[in] Specifies whether the preferred segment is set to a new value.

### -field SetUnmoveable

[in] When set, the driver will update the [**Unmoveable**](ns-d3dukmdt-d3dddi_updateallocproperty_flags.md) property of the allocation to indicate that the allocation is unmoveable.

### -field Reserved

This member is reserved and should be set to zero.

### -field PropertyMaskValue

[in] A member in the union that is contained in D3DDDI_UPDATEALLOCPROPERTY that can hold one 32-bit value that identifies how to update an allocation.

## -see-also

[**D3DDDI_UPDATEALLOCPROPERTY_FLAGS**](ns-d3dukmdt-d3dddi_updateallocproperty_flags.md)

[**D3DKMTUpdateAllocationProperty**](../d3dkmthk/nf-d3dkmthk-d3dkmtupdateallocationproperty.md)
