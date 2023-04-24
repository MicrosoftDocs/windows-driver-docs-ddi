---
UID: NS:d3dkmddi._DXGKARG_PRESENT
title: DXGKARG_PRESENT (d3dkmddi.h)
description: The DXGKARG_PRESENT structure describes a source-to-primary copy operation.
old-location: display\dxgkarg_present.htm
ms.date: 10/06/2022
keywords: ["DXGKARG_PRESENT structure"]
ms.keywords: "*INOUT_PDXGKARG_PRESENT, DXGKARG_PRESENT, DXGKARG_PRESENT structure [Display Devices], DmStructs_cbe9fbba-047c-468e-bb52-0f90c4e2b75c.xml, _DXGKARG_PRESENT, d3dkmddi/DXGKARG_PRESENT, display.dxgkarg_present"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: DXGKARG_PRESENT
f1_keywords:
 - _DXGKARG_PRESENT
 - d3dkmddi/_DXGKARG_PRESENT
 - DXGKARG_PRESENT
 - d3dkmddi/DXGKARG_PRESENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_PRESENT
 - DXGKARG_PRESENT
ms.custom: engagement-fy23
---

# DXGKARG_PRESENT structure

## -description

The **DXGKARG_PRESENT** structure describes a source-to-primary copy operation.

## -struct-fields

### -field pDmaBuffer [out]

A pointer to the start of the DMA buffer, which is aligned on 4 KB. This buffer can be sent through DMA to the graphics hardware. Before the display miniport driver returns from the [**DxgkDdiPresent**](nc-d3dkmddi-dxgkddi_present.md) function, the driver should set **pDmaBuffer** to the next empty byte that follows the last byte that the driver wrote to, or the driver should point to the location (one byte beyond the buffer space) if no more space is available. This location would have been correct if the buffer was large enough.

### -field DmaSize [in]

The size, in bytes, of the DMA buffer that **pDmaBuffer** points to.

### -field pDmaBufferPrivateData [in]

A pointer to a driver-resident private data structure that is associated with the DMA buffer that **pDmaBuffer** points to.

### -field DmaBufferPrivateDataSize [in]

The number of bytes that remain in the private data structure that **pDmaBufferPrivateData** points to for the current operation.

### -field pAllocationInfo [in]

Reserved for system use. The display miniport driver should ignore this member. This member is available beginning with Windows 7.

### -field pPresentMultiPlaneOverlayInfo [in]

A pointer to a structure of type [**DXGK_PRESENTMULTIPLANEOVERLAYINFO**](ns-d3dkmddi-_dxgk_presentmultiplaneoverlayinfo.md) that specifies info on a VidPN input and an overlay plane to display.

Supported starting with Windows 8.

### -field pAllocationList [in]

An array of [**DXGK_ALLOCATIONLIST**](ns-d3dkmddi-_dxgk_allocationlist.md) structures that describe the source, destination, or both for the copy operation. The driver accesses the source allocation handle through the **hDeviceSpecificAllocation** member of the **pAllocationList**[DXGK_PRESENT_SOURCE_INDEX] element (that is, element 1). The driver accesses the destination allocation handle through the **hDeviceSpecificAllocation** member of the **pAllocationList**[DXGK_PRESENT_DESTINATION_INDEX] element (that is, element 2).

The handles that are specified in the elements of the allocation list are the device-specific handles that the driver's [**DxgkDdiOpenAllocation**](nc-d3dkmddi-dxgkddi_openallocationinfo.md) function returned when the allocations were opened. If a source or destination is not present for the operation, the **hDeviceSpecificAllocation** member of the respective element is **NULL**. This member is available beginning with Windows 7.

> [!NOTE]
> The **hDeviceSpecificAllocation** member of the first element in the allocation list (element 0) is always **NULL**.

### -field pPatchLocationListOut [in/out]

An array of [**D3DDDI_PATCHLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist.md) structures for the patch-location list that the display miniport driver fills. Before the driver returns from a call to its [**DxgkDdiPresent**](nc-d3dkmddi-dxgkddi_present.md) function, the driver must set **pPatchLocationListOut** to the next D3DDDI_PATCHLOCATIONLIST element that follows the last D3DDDI_PATCHLOCATIONLIST element that the driver updated.

### -field PatchLocationListOutSize [in]

The number of elements in the patch-location list that **pPatchLocationListOut** specifies. The display miniport driver is not required to fill all of the elements in the entire list; the driver must use only elements that are necessary to describe the patch location within the DMA buffer.

### -field MultipassOffset [in/out]

A UINT value that specifies the progress of the copying operation if the display miniport driver's [**DxgkDdiPresent**](nc-d3dkmddi-dxgkddi_present.md) function must return STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER to obtain a new DMA buffer. When the driver's **DxgkDdiPresent** function is first called with a new [**RECT**](/windows/win32/api/windef/ns-windef-rect) list, **MultipassOffset** is initialized to zero. Before the driver returns from the **DxgkDdiPresent** call, the driver sets **MultipassOffset** to show copy progress for subsequent **DxgkDdiPresent** calls with the same command buffer. The Microsoft DirectX graphics kernel subsystem does not change the value further.

### -field Color [in]

The A8R8G8B8 color in either a color-fill operation, which is specified by the **ColorFill** bit-field flag set in the **Flags** member, or a color-key operation, which is specified by either the **SrcColorKey** or **DstColorKey** bit-field flag. Note that only one of the **ColorFill**, **SrcColorKey**, and **DstColorKey** bit-field flags is set at any time.

If the primary format is palettized RGB, **Color** contains the palette index rather than the D3DDDIFMT_A8R8G8B8 value from the [**D3DDDIFORMAT**](../d3dukmdt/ne-d3dukmdt-_d3dddiformat.md) enumeration type.

### -field DstRect [in]

A [**RECT**](/windows/win32/api/windef/ns-windef-rect) structure for the destination rectangle that is used to calculate the stretch factor.

### -field SrcRect [in]

A RECT structure for the source rectangle that is used to calculate the stretch factor.

### -field SubRectCnt [in]

The number of destination sub-rectangles in the array that **pDstSubRects** specifies.

### -field pDstSubRects [in]

An array of RECT structures for the list of destination sub-rectangles that the **DxgkDdiPresent** function copies to.

### -field FlipInterval [in]

A [**D3DDDI_FLIPINTERVAL_TYPE**](../d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type.md)-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs).

### -field Flags [in]

A [**DXGK_PRESENTFLAGS**](ns-d3dkmddi-_dxgk_presentflags.md) structure that identifies, in bit-field flags, the type of present operation to perform. Note that the **ColorFill**, **SrcColorKey**, and **DstColorKey** bit-field flags in **Flags** are mutually exclusive.

### -field DmaBufferSegmentId [in]

The identifier of the memory segment that the DMA buffer was paged in. If the identifier is zero, the DMA buffer is not correctly paged in.

### -field DmaBufferPhysicalAddress [in]

A **PHYSICAL_ADDRESS** data type (which is defined as **LARGE_INTEGER**) that indicates the physical address where the DMA buffer was paged in. If the physical address is zero, the DMA buffer is not correctly paged in.

### -field Reserved [in]

Reserved for system use. The driver should ignore this member.

### -field DmaBufferGpuVirtualAddress

A **D3DGPU_VIRTUAL_ADDRESS** data type that indicates the virtual address where the DMA buffer was paged in. If the physical address is zero, the DMA buffer is not correctly paged in.

### -field NumSrcAllocations

The number of context allocations in the source.

### -field NumDstAllocations

The number of context allocations in the destination.

### -field PrivateDriverDataSize

The size of *pPrivateDriverData*.

### -field pPrivateDriverData

Pointer to a buffer that contains optional private driver data.

## -remarks

The ratio of the source and destination rectangular areas that the **SrcRect** and **DstRect** members specify is used to compute a stretch factor. The driver can factor in the stretch-factor calculation when it performs the copy operation.

The driver is not required to perform any clipping. The Microsoft DirectX graphics kernel subsystem preclips the list of destination sub-rectangles that the **pDstSubRects** member specifies  to the coordinates of the destination rectangle that the **DstRect** member specifies and to the screen (primary). Note that if a list of destination sub-rectangles is supplied in **pDstSubRects**, the driver should use only **SrcRect** and **DstRect** to compute the stretch factor and should use the coordinates of the destination sub-rectangles for the actual copy operation.

## -see-also

[**D3DDDI_FLIPINTERVAL_TYPE**](../d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type.md)

[**D3DDDI_PATCHLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist.md)

[**DXGK_ALLOCATIONLIST**](ns-d3dkmddi-_dxgk_allocationlist.md)

[**DXGK_PRESENTFLAGS**](ns-d3dkmddi-_dxgk_presentflags.md)

[**DXGK_PRESENTMULTIPLANEOVERLAYINFO**](ns-d3dkmddi-_dxgk_presentmultiplaneoverlayinfo.md)

[**DxgkDdiPresent**](nc-d3dkmddi-dxgkddi_present.md)

[**RECT**](/windows/win32/api/windef/ns-windef-rect)
