---
UID: NS:d3dukmdt._D3DDDI_SEGMENTPREFERENCE
title: D3DDDI_SEGMENTPREFERENCE (d3dukmdt.h)
description: Learn more about the D3DDDI_SEGMENTPREFERENCE structure.
ms.date: 01/22/2024
keywords: ["D3DDDI_SEGMENTPREFERENCE structure"]
ms.keywords: _D3DDDI_SEGMENTPREFERENCE, D3DDDI_SEGMENTPREFERENCE,
req.header: d3dukmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DDDI_SEGMENTPREFERENCE
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DDDI_SEGMENTPREFERENCE
 - d3dukmdt/_D3DDDI_SEGMENTPREFERENCE
 - D3DDDI_SEGMENTPREFERENCE
 - d3dukmdt/D3DDDI_SEGMENTPREFERENCE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_SEGMENTPREFERENCE
 - D3DDDI_SEGMENTPREFERENCE
dev_langs:
 - c++
---

# D3DDDI_SEGMENTPREFERENCE structure

## -description

The **D3DDI_SEGMENTPREFERENCE** structure describes the preferred segment for this allocation being created.

## -struct-fields

### -field SegmentId0

The identifier of the highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to the first 5 bits of the **Value** member.

### -field Direction0

Set to zero to indicate that *VidMm* chooses which end of **SegmentId0** to do the allocation from. This member is equivalent to the sixth bit of the **Value** member.

### -field SegmentId1

The identifier of the next highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to bits 7 through 11 of the **Value** member.

### -field Direction1

Set to zero to indicate that *VidMm* chooses which end of **SegmentId1** to do the allocation from. This member is equivalent to the 12th bit of the **Value** member.

### -field SegmentId2

The identifier of the next highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to bits 13 through 17 of the **Value** member.

### -field Direction2

Set to zero to indicate that *VidMm* chooses which end of **SegmentId2** to do the allocation from. This member is equivalent to the 18th bit of the **Value** member.

### -field SegmentId3

The identifier of the next highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to bits 19 through 23 of the **Value** member.

### -field Direction3

Set to zero to indicate that *VidMm* chooses which end of **SegmentId3** to do the allocation from. This member is equivalent to the 24th bit of the **Value** member.

### -field SegmentId4

The identifier of the next highest priority preferred segment, or zero if no preferred segment is required. Valid values are from 0 through 31. This member is equivalent to bits 25 through 29 of the **Value** member.

### -field Direction4

Set to zero to indicate that *VidMm* chooses which end of **SegmentId4** to do the allocation from. This member is equivalent to the 30th bit of the **Value** member.

### -field Reserved

Reserved (bits 31-32).

### -field Value

An alternative way to access the segment preference information.

## -remarks

The segment preference is used when allocating memory. When user mode (for example, the D3D runtime) calls [**D3DKMTCreateAllocation**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation.md), the UMD provides private driver data describing the allocation. *Dxgkrnl* takes this private driver data and passes it to the KMD who then fills out a description of each allocation in a way understood by *VidMm*. The UMD data contains information such as the resource type (texture, swapchain, etc). The KMD translates this data to things like size, alignment, a set of memory segments that the allocation can be located, preferences for these segments (as indicated by this structure), and so forth.

## -see-also

[**D3DKMTCreateAllocation**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation.md)

[**D3DKMTUpdateAllocationProperty**](../d3dkmthk/nf-d3dkmthk-d3dkmtupdateallocationproperty.md)
