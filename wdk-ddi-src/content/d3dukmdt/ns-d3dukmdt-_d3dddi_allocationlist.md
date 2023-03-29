---
UID: NS:d3dukmdt._D3DDDI_ALLOCATIONLIST
title: D3DDDI_ALLOCATIONLIST (d3dukmdt.h)
description: Learn more about the D3DDDI_ALLOCATIONLIST structure.
tech.root: display
ms.date: 03/28/2023
keywords: ["D3DDDI_ALLOCATIONLIST structure"]
ms.keywords: D3DDDI_ALLOCATIONLIST, D3DDDI_ALLOCATIONLIST structure [Display Devices], D3D_other_Structs_0e766b30-b39d-4107-8739-0b9290e7d489.xml, _D3DDDI_ALLOCATIONLIST, d3dukmdt/D3DDDI_ALLOCATIONLIST, display.d3dddi_allocationlist
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DDDI_ALLOCATIONLIST
f1_keywords:
 - _D3DDDI_ALLOCATIONLIST
 - d3dukmdt/_D3DDDI_ALLOCATIONLIST
 - D3DDDI_ALLOCATIONLIST
 - d3dukmdt/D3DDDI_ALLOCATIONLIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_ALLOCATIONLIST
 - D3DDDI_ALLOCATIONLIST
---

# D3DDDI_ALLOCATIONLIST structure

## -description

The **D3DDDI_ALLOCATIONLIST** structure describes information about an allocation specification that is used in direct memory access (DMA) buffering.

## -struct-fields

### -field hAllocation

[in] The allocation handle returned by the [**D3DKMTOpenResource**](../d3dkmthk/nf-d3dkmthk-d3dkmtopenresource.md) function in the **hAllocation** member of the [**D3DDDI_OPENALLOCATIONINFO**](ns-d3dukmdt-_d3dddi_openallocationinfo.md)   structure, or by the [**D3DKMTCreateAllocation**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation.md) function in the **hAllocation** member of the [**D3DDDI_ALLOCATIONINFO**](ns-d3dukmdt-_d3dddi_allocationinfo.md) structure.

### -field WriteOperation

[in] A UINT that can hold information about whether the allocation can be written to. Setting to 1 indicates the allocation can be written to.

Setting this member is equivalent to setting the first bit of the 32-bit **Value** member (0x00000001).

### -field DoNotRetireInstance

[in] A UINT that can hold information about whether the allocation can be retired. Setting to 1 indicates that the video memory manager should not retire the instance of the allocation because the driver will reference it again in a subsequent DMA buffer (for example, a manual broadcast of a DMA buffer to multiple contexts). All instances of an allocation are eventually retired. This flag is rarely used.

Setting this member is equivalent to setting the second bit of the 32-bit **Value** member (0x00000002).

### -field OfferPriority

[in] A value from the [**D3DDDI_OFFER_PRIORITY**](ne-d3dukmdt-_d3dddi_offer_priority.md) enumeration that indicates the importance of video memory resources  that the user-mode display driver offers for reuse.

If **OfferPriority** does not have a value of **D3DDDI_OFFER_PRIORITY_NONE**, the allocation is considered to be offered after the DMA buffer is processed.

Setting this member is equivalent to setting bits 3 through 5 of the 32-bit **Value** member (0x0000001C).

Supported starting with Windows 8.

### -field Reserved

[in] This member is reserved and should be set to zero.

### -field Value

[in] A 32-bit value that identifies information about an allocation specification used in DMA buffering.

## -see-also

[**CreateDevice**](../d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice.md)

[**D3DDDIARG_CREATEDEVICE**](../d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice.md)

[**D3DDDICB_RENDER**](../d3dumddi/ns-d3dumddi-_d3dddicb_render.md)

[**D3DDDI_OFFER_PRIORITY**](ne-d3dukmdt-_d3dddi_offer_priority.md)

[**pfnRenderCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb.md)
