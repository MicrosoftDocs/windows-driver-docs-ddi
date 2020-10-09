---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_TIER_0020
title: D3D12DDI_VIDEO_DECODE_TIER_0020 (d3d12umddi.h)
description: Specifies the video decode tier.
old-location: display\d3d12ddi_video_decode_tier.htm
ms.assetid: CC4B83A3-1F57-493F-840F-F0F799B631E6
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_DECODE_TIER_0020 enumeration"]
ms.keywords: D3D12DDI_VIDEO_DECODE_TIER_0020, D3D12DDI_VIDEO_DECODE_TIER_0020 enumeration [Display Devices], D3D12DDI_VIDEO_DECODE_TIER_0020_1, D3D12DDI_VIDEO_DECODE_TIER_0020_2, D3D12DDI_VIDEO_DECODE_TIER_0020_3, D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_1, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_2, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_3, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED, display.d3d12ddi_video_decode_tier
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_TIER_0020
f1_keywords:
 - D3D12DDI_VIDEO_DECODE_TIER_0020
 - d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_DECODE_TIER_0020
---

# D3D12DDI_VIDEO_DECODE_TIER_0020 enumeration

## -description

Specifies the video decode tier. Decode video tiers define a set of hardware capabilities. The higher the tier, the more capable the hardware.

## -enum-fields

### -field D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED

The decode profile is not supported.

### -field D3D12DDI_VIDEO_DECODE_TIER_0020_1

Video decode tier 1. In video decode tier 1, hardware requires decode output textures and reference textures for decoding a stream to be physically contiguous when video operations reference them.

The reference resources are allocated by the application as a D3D12 texture array. The driver does not receive explicit hints that the allocation targets video scenarios and may initially allocate non-physically contiguous memory. Drivers are expected to use a new [Update Allocation Properties](/windows-hardware/test/hlk/testref/51f5ec4f-bfcb-41c2-bb01-fef1403c93e4) feature provided by the memory manager, to schedule a conversion to physically contiguous upon submission of the video work that actually requires it to be physically contiguous.

Hardware characteristics that place hardware in Tier 1:

* Decode hardware requires physically contiguous memory for decode output and references. Input buffers with the compressed bitstream may also require physically contiguous.

* Decode hardware may have a special tiling format or other memory layout definition that is incompatible with other engines or video operations.

Compressed input buffer requirements:

* All slices for a given frame must be placed in order and contiguous (no gaps between slices).

* Drivers must not perform additional copies of the bitstream data.

* The first slice must begin on a 128-byte boundary.

* Hardware must support decoding from a buffer allocated from D3D12DDI_MEMORY_POOL_L0 (always system memory).

* Hardware must support decoding from D3D12DDI_MEMORY_POOL_L1 (default pool) with D3D12DDI_CPU_PAGE_PROPERTY_NOT_AVAILABLE.

### -field D3D12DDI_VIDEO_DECODE_TIER_0020_2

Video decode tier 2. Decode tier 2 allows the caller to allocate reference and output textures as separate 2D texture resources. The application is no longer required to allocate texture arrays, but this must be supported.

Decode Tier 2 does not have physically contiguous requirements. Hardware may have contiguous VA (video decoding acceleration) requirements in this tier, and applications are required to create a texture array to support this.

To enable Tier 2, reserved resources, also called Tiled or Sparse resources, must be supported for the reference and output formats that are supported by the driver. This can be done in two ways:

* If hardware has support for per-process GPU VA and has a tile pattern that supports the tile shape requirements of reserved resources, the pre-existing D3D12 tiled resource mechanism can be used.

* If hardware has support for per-process GPU VA, but the tile pattern does not conform to the tile shape requirements of reserved resources, and hardware can support a tile mapping that maps and unmaps tiles for an entire subresource, for each plane of a planar resource that is a separate subresource in D3D12, the mechanism requires that they can be tile mapped and tile unmapped independently. Note that this mechanism is in development, but will obfuscate tile shape at the API.

Hardware characteristics that place hardware in Tier 2:

* Does not require physically contiguous memory.

* Hardware has a contiguous VA requirement.

* Decode hardware may have a special tiling format or other memory layout definition that is incompatible with other engines or video operations.

The compressed input buffer requirements are the same as Tier 1.

### -field D3D12DDI_VIDEO_DECODE_TIER_0020_3

Video decode tier 3. This tier is supported started in WDDM 2.3.

Decode Tier 3 allows the caller to allocate reference and output textures as standard 2D texture resources. The application is no longer required to allocate texture arrays, but this must be supported.

Decode Tier 3 does not require physically contiguous allocations.  Hardware must no longer require the D3D12DDI_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY, but must still support it. When queried, the D3D12DDI_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY member of the [D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020](ns-d3d12umddi-d3d12ddi_video_decode_support_data_0020.md) structure must be set to FALSE.

To enable Tier 3, reserved resources (also called Tiled or Sparse resources) must be supported for the reference and output formats supported by the driver. This can happen in two ways:

* If hardware has support for per-process GPU VA and has a tile pattern that supports the tile shape requirements of reserved resources, the pre-existing D3D12 tiled resource mechanism can be used.

* If hardware has support for per-process GPU VA, but the tile pattern does not conform to the tile shape requirements of reserved resources, and hardware can support a tile mapping that maps and unmaps tiles for an entire subresource, for each plane of a planar resource that is a separate subresource in D3D12, the mechanism requires that they can be tile mapped and tile unmapped independently. Note that this mechanism is in development, but will obfuscate tile shape at the API.

The compressed input buffer requirements are the same as Tier 1.

## -remarks

If decode hardware requires a unique tiling format that is not supported for operations on other engines or different video operations, the decoder may set D3D12DDI_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY in the [D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020](ns-d3d12umddi-d3d12ddi_video_decode_support_data_0020.md) structure when querying for profile support. This flag indicates that the application must allocate references with the D3D12DDI_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY flag. If the output is needed as a future reference frame, the output frame passed to PFND3D12DDI_VIDEO_DECODE_FRAME is a D3D12 resource that can be consumed by other portions of the pipeline, and must not have the D3D12DDI_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY flag.

The following table shows the different capabilities for each tier:

| Capability | Tier 1 | Tier 2 | Tier 3 |
| ---------- | ------ | ------ | ------ |
| Supports individually allocated reference frames and output. | No | No | Required |
| Supports references and allocated as a texture array. | Required | Required | Required |
| May optionally require the REFERENCE_ONLY resource flag. Note that all tiers are required to work with flag present, even when its not required. | Optional | Optional | No |
| Support for references allocated with REFERENCE_ONLY, even when caps do not require it. | Required | Required | Required |
| Supports Tiled/Sparse resources for references, input and output. | No | Required | Required |
| Compressed bit stream input buffers may be allocated as L0 (main system memory) or L1 (for dGPU, video memory). | Required | Required | Required |
| Requires compressed bitstream data for slices to be located in a single buffer allocation with no gaps between slices. | Required | Required | Required |
| Offset to first slice in the  compressed input buffer must be 256 byte aligned. | Required | Required | Required |
| Drivers must not perform additional copies of the compressed bitstream data. | Required | Required | Required |