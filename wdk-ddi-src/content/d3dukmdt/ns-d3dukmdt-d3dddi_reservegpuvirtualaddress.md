---
UID: NS:d3dukmdt.D3DDDI_RESERVEGPUVIRTUALADDRESS
title: D3DDDI_RESERVEGPUVIRTUALADDRESS (d3dukmdt.h)
description: Learn more about the D3DDDI_RESERVEGPUVIRTUALADDRESS structure.
tech.root: display
ms.date: 07/19/2024
keywords: ["D3DDDI_RESERVEGPUVIRTUALADDRESS structure"]
ms.keywords: D3DDDI_RESERVEGPUVIRTUALADDRESS, D3DDDI_RESERVEGPUVIRTUALADDRESS structure [Display Devices], d3dukmdt/D3DDDI_RESERVEGPUVIRTUALADDRESS, display.d3dddi_reservegpuvirtualaddress
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
req.typenames: D3DDDI_RESERVEGPUVIRTUALADDRESS
f1_keywords:
 - D3DDDI_RESERVEGPUVIRTUALADDRESS
 - d3dukmdt/D3DDDI_RESERVEGPUVIRTUALADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDI_RESERVEGPUVIRTUALADDRESS
---

# D3DDDI_RESERVEGPUVIRTUALADDRESS structure

## -description

The user-mode graphics driver passes **D3DDDI_RESERVEGPUVIRTUALADDRESS** to the D3D runtime's [**pfnReserveGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md) callback to reserve an address range in the GPU virtual address space of the current process.

## -struct-fields

### -field hPagingQueue

This member is obsolete. Don't use it.

### -field hAdapter

[in] DirectX graphics adapter handle or zero (0). If UMD sets **hAdapter** set to 0, the D3D runtime will set **hAdapter** to the kernel's D3DKMT_HANDLE before calling the [**D3DKMTReserveGpuVirtualAddress**](../d3dkmthk/nf-d3dkmthk-d3dkmtreservegpuvirtualaddress.md) kernel interface.

### -field BaseAddress

[in/optional] The number of bytes to reserve in the GPU virtual address space. **BaseAddress** must be aligned to a 64KB boundary.

If **BaseAddress** is non-NULL, the video memory manager attempts to use this address as the base address for the reserved range. If the range from **BaseAddress** to **BaseAddress**+**Size** isn’t free, the call fails. When **BaseAddress** is non-NULL, **MinimumAddress** and **MaximumAddress** are ignored.

If NULL is specified the video memory manager picks the base address for the allocation within the specified **MinimumAddress** and **MaximumAddress**.

### -field MinimumAddress

[in/optional] The minimum GPU virtual address to consider for the reserved range. **MinimumAddress** is in bytes and must be aligned to 64KB boundary. It's ignored when **BaseAddress** is non-NULL.

### -field MaximumAddress

[in/optional] The maximum GPU virtual address to consider for the reserved range. The video memory manager guarantees that **BaseAddress**+**Size** <= **MaximumAddress**. If **MaximumAddress** is set to NULL the video memory manager will not apply any limit.

**MaximumAddress** is in bytes and must be aligned to 64KB boundary. It's ignored when **BaseAddress** is non-NULL.

### -field Size

[in] The size of the range to reserve, in bytes. Must be a multiple of 64KB.

### -field ReservationType

This member is obsolete. Don't use it.

### -field Reserved0

This member is reserved and should be set to zero.

### -field DriverProtection

This member is obsolete. Don't use it.

### -field Reserved1

This member is reserved and should be set to zero.

### -field VirtualAddress

[out] The reserved virtual address.

### -field PagingFenceValue

This member is obsolete. Don't use it.

### -field Reserved2

This member is reserved and should be set to zero.

## -see-also

[**pfnReserveGpuVirtualAddressCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md)
