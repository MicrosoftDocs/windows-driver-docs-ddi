---
UID: NS:d3dkmddi._DXGKARGCB_MAPFRAMEBUFFERPOINTER
title: DXGKARGCB_MAPFRAMEBUFFERPOINTER (d3dkmddi.h)
description: The DXGKARGCB_MAPFRAMEBUFFERPOINTER structure contains the arguments used by the DXGKCB_MAPFRAMEBUFFERPOINTER callback function to map a frame buffer pointer.
ms.date: 10/13/2021
keywords: ["DXGKARGCB_MAPFRAMEBUFFERPOINTER structure"]
ms.keywords: _DXGKARGCB_MAPFRAMEBUFFERPOINTER, DXGKARGCB_MAPFRAMEBUFFERPOINTER, *INOUT_PDXGKARGCB_MAPFRAMEBUFFERPOINTER
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARGCB_MAPFRAMEBUFFERPOINTER
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_MAPFRAMEBUFFERPOINTER
 - d3dkmddi/_DXGKARGCB_MAPFRAMEBUFFERPOINTER
 - DXGKARGCB_MAPFRAMEBUFFERPOINTER
 - d3dkmddi/DXGKARGCB_MAPFRAMEBUFFERPOINTER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_MAPFRAMEBUFFERPOINTER
 - DXGKARGCB_MAPFRAMEBUFFERPOINTER
product:
 - Windows
---

# DXGKARGCB_MAPFRAMEBUFFERPOINTER structure

## -description

The **DXGKARGCB_MAPFRAMEBUFFERPOINTER** structure contains arguments used by the [**DXGKCB_MAPFRAMEBUFFERPOINTER**](nc-d3dkmddi-dxgkcb_mapframebufferpointer.md) callback function to map a frame buffer pointer.

## -struct-fields

### -field PhysicalAdapterIndex [in]

The index of the physical adapter.

### -field Size [in]

The size, in bytes, of the mapped subregion of the section object. **Size** must be a multiple of PAGE_SIZE.

### -field Offset [in/out]

On input, this is the offset, in bytes, to the mapped subregion of the section object. Offset must be a multiple of PAGE_SIZE. On output, this is the offset from the output base address to which the driver should copy the data.

### -field pBaseAddress [out]

A CPU accessible base address pointer to the mapped subregion of the section object. The driver must add the output **Offset** value to the base address to get the destination address of any copy operations (pDestinationAddress = pBaseAddress + Offset).

## -remarks

If pinning the entire frame buffer’s section object fails, the driver must try to ensure forward progress by performing the transfer in smaller pieces. This is accomplished by allocating a small MDL or chunk of memory during initialization time which can be used to transfer the contents from the hardware, and then calling **DXGKCB_MAPFRAMEBUFFERPOINTER** to obtain a pointer to a subregion of the section object.

The driver is responsible for copying the data from the pre-allocated buffer to the mapped subregion. The reverse is also true when restoring the frame buffer contents.

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_MAPFRAMEBUFFERPOINTER**](nc-d3dkmddi-dxgkcb_mapframebufferpointer.md)
