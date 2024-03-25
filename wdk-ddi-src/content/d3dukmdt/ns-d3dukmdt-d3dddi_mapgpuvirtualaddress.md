---
UID: NS:d3dukmdt.D3DDDI_MAPGPUVIRTUALADDRESS
title: D3DDDI_MAPGPUVIRTUALADDRESS (d3dukmdt.h)
description: Learn more about the D3DDDI_MAPGPUVIRTUALADDRESS structure.
tech.root: display
ms.date: 07/25/2023
keywords: ["D3DDDI_MAPGPUVIRTUALADDRESS structure"]
ms.keywords: D3DDDI_MAPGPUVIRTUALADDRESS, D3DDDI_MAPGPUVIRTUALADDRESS structure [Display Devices], Execute, NoAccess, Write, Zero, d3dukmdt/D3DDDI_MAPGPUVIRTUALADDRESS, display.d3dddi_mapgpuvirtualaddress
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: D3DDDI_MAPGPUVIRTUALADDRESS
f1_keywords:
 - D3DDDI_MAPGPUVIRTUALADDRESS
 - d3dukmdt/D3DDDI_MAPGPUVIRTUALADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDI_MAPGPUVIRTUALADDRESS
---

# D3DDDI_MAPGPUVIRTUALADDRESS structure

## -description

The **D3DDDI_MAPGPUVIRTUALADDRESS** structure is used with [**pfnMapGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md) to map a GPU virtual address range to a specific allocation range or to put it to the [*Invalid* or *Zero*](../d3dukmdt/ns-d3dukmdt-_d3dddigpuvirtualaddress_protection_type.md) state.

## -struct-fields

### -field hPagingQueue

A handle for the device paging queue, used for the operation.

### -field BaseAddress

(Optional) If non-NULL, the video memory manager will attempt to use this address as the base address for the mapping. If the range from **BaseAddress** to **BaseAddress**+**Size** isn’t free, it must belong to a range, previously obtained by calling [**pfnReserveGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md) or [**pfnMapGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md).

The **BaseAddress** value is in bytes and must be aligned to CPU page boundary.
If NULL is specified, the video memory manager will pick the base address for the allocation within the specified **MinimumAddress** and **MaximumAddress**.

### -field MinimumAddress

(Optional) Specifies the minimum GPU virtual address to consider for the mapped range.

The **MinimumAddress** value is in bytes and must be aligned to 4KB page. This parameter is ignored when **BaseAddress** != NULL.

### -field MaximumAddress

(Optional) Specifies the maximum GPU virtual address to consider for the mapped range. the video memory manager will guarantee that **BaseAddress**+**Size** <= **MaximumAddress**. If **MaximumAddress** is set to NULL the video memory manager will not apply any limit.

The **MaximumAddress** value is in bytes and must be aligned to the 4KB page. This parameter is ignored when **BaseAddress** != NULL.

### -field hAllocation

Handle to the allocation being mapped into the GPU virtual address space. Must be NULL when **Protection.NoAccess** or **Protection.Zero** is specified.

### -field OffsetInPages

Specifies the offset, in 4KB, to the starting page within the specified allocation that must be mapped.

### -field SizeInPages

Specifies the size of the range to map, in 4KB pages.

### -field Protection

A [**D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE**](ns-d3dukmdt-_d3dddigpuvirtualaddress_protection_type.md) structure that specifies the protection on the GPU virtual address that is mapped.

### -field DriverProtection

Specifies a driver-specific, 64-bit protection value associated with the VA range being allocated. The specified driver protection will be used in call to [**DxgkDdiUpdatePageTable**](/windows-hardware/drivers/display/dxgkddiupdatepagetable) for page table entries corresponding to this virtual address range.

### -field Reserved0

This member is reserved and should be set to zero.

### -field Reserved1

This member is reserved and should be set to zero.

### -field VirtualAddress

The virtual address assigned to the allocation.

### -field PagingFenceValue

The device paging fence value that the video memory manager signals when the map operation completes on the GPU. The user-mode driver must ensure that this fence is retired or explicitly wait on either the CPU or the GPU on that fence before allowing the GPU to access the mapped range or an unrecoverable fault might occur.
A zero fence value might be returned, meaning that the operation is already completed.

## -see-also

[**D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE**](ns-d3dukmdt-_d3dddigpuvirtualaddress_protection_type.md)

[**D3DKMTMapGpuVirtualAddress**](../d3dkmthk/nf-d3dkmthk-d3dkmtmapgpuvirtualaddress.md)

[**DxgkDdiUpdatePageTable**](/windows-hardware/drivers/display/dxgkddiupdatepagetable)

[**pfnMapGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md)

[**pfnReserveGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md)
