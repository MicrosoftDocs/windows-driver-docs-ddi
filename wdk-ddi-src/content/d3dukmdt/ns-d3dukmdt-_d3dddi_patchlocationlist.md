---
UID: NS:d3dukmdt._D3DDDI_PATCHLOCATIONLIST
title: _D3DDDI_PATCHLOCATIONLIST (d3dukmdt.h)
description: The D3DDDI_PATCHLOCATIONLIST structure describes the location of an allocation to patch (that is, assign a physical address to the allocation).
old-location: display\d3dddi_patchlocationlist.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDI_PATCHLOCATIONLIST structure"]
ms.keywords: D3DDDI_PATCHLOCATIONLIST, D3DDDI_PATCHLOCATIONLIST structure [Display Devices], D3D_other_Structs_30473342-0122-445f-81c0-9cf5c62c771e.xml, _D3DDDI_PATCHLOCATIONLIST, d3dukmdt/D3DDDI_PATCHLOCATIONLIST, display.d3dddi_patchlocationlist
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
targetos: Windows
req.typenames: D3DDDI_PATCHLOCATIONLIST
f1_keywords:
 - _D3DDDI_PATCHLOCATIONLIST
 - d3dukmdt/_D3DDDI_PATCHLOCATIONLIST
 - D3DDDI_PATCHLOCATIONLIST
 - d3dukmdt/D3DDDI_PATCHLOCATIONLIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_PATCHLOCATIONLIST
 - D3DDDI_PATCHLOCATIONLIST
---

# _D3DDDI_PATCHLOCATIONLIST structure


## -description

The D3DDDI_PATCHLOCATIONLIST structure describes the location of an allocation to patch (that is, assign a physical address to the allocation).

## -struct-fields

### -field AllocationIndex

[in] An index of the element in the allocation list that specifies the allocation that is referenced by the patch location.

### -field SlotId

[in/out] A UINT that identifies the slot where the allocation will reside. Resources with identical slot identifiers can replace each other.

Setting this member is equivalent to setting bits in the first 24 bits of the 32-bit <b>Value</b> member (0x00FFFFFF).

### -field Reserved

[in] This member is reserved and should be set to zero. 

Setting this member to zero is equivalent to setting the remaining 8 bits (0xFF000000) of the 32-bit <b>Value</b> member to zeros.

### -field Value

[in] A 32-bit value that identifies the location of an allocation to patch.

### -field DriverId

[in/out] The driver-defined identifier of the allocation specification.

### -field AllocationOffset

[in/out] The starting offset, in bytes, within the allocation that is referenced.

### -field PatchOffset

[in/out] The offset, in bytes, into the DMA buffer that must be patched.

### -field SplitOffset

[in/out] The offset, in bytes, where the DMA buffer must be split if the allocation cannot be brought into video memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_render">D3DDDICB_RENDER</a>



<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>

