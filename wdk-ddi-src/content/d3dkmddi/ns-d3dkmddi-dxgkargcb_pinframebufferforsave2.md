---
UID: NS:d3dkmddi._DXGKARGCB_PINFRAMEBUFFERFORSAVE2
tech.root: display
title: DXGKARGCB_PINFRAMEBUFFERFORSAVE2
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The DXGKARGCB_PINFRAMEBUFFERFORSAVE2 structure contains the information used by the DxgkCbPinFrameBufferForSave2 callback function to pin an entire frame buffer at once.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXGKARGCB_PINFRAMEBUFFERFORSAVE2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_PINFRAMEBUFFERFORSAVE2
 - DXGKARGCB_PINFRAMEBUFFERFORSAVE2
f1_keywords:
 - _DXGKARGCB_PINFRAMEBUFFERFORSAVE2
 - d3dkmddi/_DXGKARGCB_PINFRAMEBUFFERFORSAVE2
 - DXGKARGCB_PINFRAMEBUFFERFORSAVE2
 - d3dkmddi/DXGKARGCB_PINFRAMEBUFFERFORSAVE2
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_PINFRAMEBUFFERFORSAVE2** structure contains the information used by the [**DxgkCbPinFrameBufferForSave2**](nc-d3dkmddi-dxgkcb_pinframebufferforsave2.md) callback function to pin an entire frame buffer at once.

## -struct-fields

### -field PhysicalAdapterIndex

[in] The index of the physical adapter.

### -field CommitSize

[in] The size, in bytes, that the driver requires to pin. This size must be a multiple of PAGE_SIZE and must be less than or equal to the maximum size specified by the driver in the [**DXGK_FRAMEBUFFERSAVEAREA**](ns-d3dkmddi-_dxgk_framebuffersavearea.md) structure when the driver's [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) callback is called with **DXGKQAITYPE_FRAMEBUFFERSAVESIZE** during driver initialization.

### -field Flags

### -field Flags.PreferContiguous

Indicates that the driver can use a contiguous address descriptor list (ADL) in this path and is preferable to a page array. When logical remapping is enabled, this may save a large amount of memory when allocating the ADL based on CommitSize. This flag behaves identically to the same-named flag in [**DXGKARGCB_ALLOCATE_ADL**](ns-d3dkmddi-dxgkargcb_allocate_adl.md) when [allocating an ADL](nc-d3dkmddi-dxgkcb_allocateadl.md).

### -field Flags.Reserved

Reserved; must be set to zero.

### -field Flags.Value

An alternative way to access the **Flags** bits.

### -field pAdl

[out] On a successful call to [**DxgkCbPinFrameBufferForSave2**](nc-d3dkmddi-dxgkcb_pinframebufferforsave2.md), points to the [**DXGK_ADL**](ns-d3dkmddi-dxgk_adl.md) structure with a list of pages of the frame buffer save area. These pages are guaranteed to be mapped to the IoMmu.

## -remarks

## -see-also

[**DXGK_ADL**](ns-d3dkmddi-dxgk_adl.md)

[**DXGK_FRAMEBUFFERSAVEAREA**](ns-d3dkmddi-_dxgk_framebuffersavearea.md)

[**DxgkCbPinFrameBufferForSave2**](nc-d3dkmddi-dxgkcb_pinframebufferforsave2.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
