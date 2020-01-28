---
UID: NS:d3dkmddi._DXGK_ALLOCATIONUSAGEINFO1
title: _DXGK_ALLOCATIONUSAGEINFO1 (d3dkmddi.h)
description: The DXGK_ALLOCATIONUSAGEINFO1 structure describes how an allocation can be used in DMA buffering.
old-location: display\dxgk_allocationusageinfo1.htm
ms.assetid: 6de3363c-fcf8-4350-acee-b401bb3f82a6
ms.date: 05/10/2018
ms.keywords: DXGK_ALLOCATIONUSAGEINFO1, DXGK_ALLOCATIONUSAGEINFO1 structure [Display Devices], DmStructs_262d3b0f-50c6-429b-9b6e-34963d2ae42b.xml, _DXGK_ALLOCATIONUSAGEINFO1, d3dkmddi/DXGK_ALLOCATIONUSAGEINFO1, display.dxgk_allocationusageinfo1
f1_keywords:
 - "d3dkmddi/DXGK_ALLOCATIONUSAGEINFO1"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_ALLOCATIONUSAGEINFO1
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_ALLOCATIONUSAGEINFO1
---

# _DXGK_ALLOCATIONUSAGEINFO1 structure


## -description


The DXGK_ALLOCATIONUSAGEINFO1 structure describes how an allocation can be used in DMA buffering.


## -struct-fields




### -field Flags

[out] A union that contains either a structure (with the first eight members that are described below) or a 32-bit value (in the <b>Value</b> member) that identifies how the allocation is used:


### -field Flags.PrivateFormat

A UINT value that specifies whether the allocation is a private vendor format.  

Setting this is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Flags.Swizzled

A UINT value that specifies whether the allocation is swizzled or tiled. 

Setting this is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Flags.MipMap

A UINT value that specifies whether the allocation is a MIP-mapped texture.

Setting this is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field Flags.Cube

A UINT value that specifies whether the allocation is a cube texture. 

Setting this is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Flags.Volume

A UINT value that specifies whether the allocation is a volume texture.

Setting this is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field Flags.Vertex

A UINT value that specifies whether the allocation is a vertex buffer.

Setting this is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field Flags.Index

A UINT value that specifies whether the allocation is an index buffer.

Setting this is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field Flags.Reserved

This member is reserved and should be set to zero. Setting this to zero is equivalent to setting the remaining 25 bits (0xFFFFFF80) of the 32-bit <b>Value</b> member to zeros.


### -field Flags.Value

Specifies a member in the union contained in the <b>Flags</b> member that can hold one 32-bit value that identifies how the allocation is used.


### -field Format

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the allocation. The <b>PrivateFormat</b> bit-field flag in the <b>Flags</b> member must be set to 0 (FALSE).


### -field PrivateFormat

[out] A private format value for the allocation. The <b>PrivateFormat</b> bit-field flag in the <b>Flags</b> member must be set to 1 (TRUE).


### -field SwizzledFormat

[out] A swizzled format value for the allocation that is private to a specific vendor.


### -field ByteOffset

[out] The offset, in bytes, into the video memory manager's allocation that marks the start of the driver's version of the allocation.


### -field Width

[out] The width, in pixels, of the allocation.


### -field Height

[out] The height, in number of lines, of the allocation.


### -field Pitch

[out] The pitch, in bytes, of the allocation--that is, the distance, in bytes, to the start of the next line.


### -field Depth

[out] The depth, in levels, of the allocation (for MIP-mapped and volume textures only).


### -field SlicePitch

[out] The slice pitch, in bytes, from level to level (for cube and volume textures only).


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationusagehint">DXGK_ALLOCATIONUSAGEHINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>
 

 

