---
UID: NS:d3dukmdt.D3DDDI_UPDATEALLOCPROPERTY
title: D3DDDI_UPDATEALLOCPROPERTY (d3dukmdt.h)
description: D3DDDI_UPDATEALLOCPROPERTY describes the parameters needed to update an allocation.
old-location: display\d3dddi_updateallocproperty.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDI_UPDATEALLOCPROPERTY structure"]
ms.keywords: D3DDDI_UPDATEALLOCPROPERTY, D3DDDI_UPDATEALLOCPROPERTY structure [Display Devices], d3dukmdt/D3DDDI_UPDATEALLOCPROPERTY, display.d3dddi_updateallocproperty
req.header: d3dukmdt.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later versions of the Windows operating systems.
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

# D3DDDI_UPDATEALLOCPROPERTY structure


## -description

D3DDDI_UPDATEALLOCPROPERTY describes the parameters needed to update an allocation.

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

A UINT value that specifies whether the allocation is accessed by its physical address.

Setting this member is equivalent to setting the first bit of the 32-bit <b>PropertyMaskValue</b> member (0x00000001).

### -field SetSupportedSegmentSet

A UINT value that specifies whether the supported segment is set to a new value.

Setting this member is equivalent to setting the second bit of the 32-bit <b>PropertyMaskValue</b> member (0x00000010).

### -field SetPreferredSegment

A UINT value that specifies whether the preferred segment is set to a new value.

Setting this member is equivalent to setting the third bit of the 32-bit <b>PropertyMaskValue</b> member (0x00000100).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFFE) of the 32-bit <b>PropertyMaskValue</b> member to zeros.

### -field PropertyMaskValue

A member in the union that is contained in D3DDDI_UPDATEALLOCPROPERTY that can hold one 32-bit value that identifies how to update an allocation.

