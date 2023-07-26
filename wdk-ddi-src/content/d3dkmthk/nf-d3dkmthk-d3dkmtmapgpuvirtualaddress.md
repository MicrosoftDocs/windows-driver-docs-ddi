---
UID: NF:d3dkmthk.D3DKMTMapGpuVirtualAddress
title: D3DKMTMapGpuVirtualAddress function (d3dkmthk.h)
description: Learn more about the D3DKMTMapGpuVirtualAddress function.
ms.date: 07/25/2023
keywords: ["D3DKMTMapGpuVirtualAddress function"]
ms.keywords: D3DKMTMapGpuVirtualAddress, D3DKMTMapGpuVirtualAddress function [Display Devices], d3dkmthk/D3DKMTMapGpuVirtualAddress, display.d3dkmtmapgpuvirtualaddress
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTMapGpuVirtualAddress
 - d3dkmthk/D3DKMTMapGpuVirtualAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - API-MS-Win-DX-D3DKMT-L1-1-1.dll
 - GDI32.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTMapGpuVirtualAddress
---

# D3DKMTMapGpuVirtualAddress function

## -description

**D3DKMTMapGpuVirtualAddress** maps a GPU virtual address range to a specific allocation range or puts it to the [*Invalid* or *Zero*](../d3dukmdt/ns-d3dukmdt-_d3dddigpuvirtualaddress_protection_type.md) state.

## -parameters

### -param unnamedParam1

[in/out] **pData** is a pointer to a [**D3DDDI_MAPGPUVIRTUALADDRESS**](../d3dukmdt/ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md) structure that describes the operation.

## -returns

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully created.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other **NTSTATUS** values.

## -remarks

The user-mode driver can specify a base GPU virtual address (VA) to map or let the video memory manager automatically pick one. When specifying a non-NULL **BaseAddress** value, the entire range from **BaseAddress** to **BaseAddress**+**Size** must be in a freed state or belong to a VA range that was obtained by calling **MapGpuVirtualAddress** or [**DxgkCbReserveGpuVirtualAddressRange**](../d3dkmddi/nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md). When **Protection.Zero** or **Protection.NoAccess** is specified, the VA range can't belong to a range that was obtained by calling **MapGpuVirtualAddressCb**.

The user-mode driver can specify whether the mapping should allow for write and execute privileges in addition to read privileges, which always exist by default.

In the linked display adapter (LDA) configuration, the paging queue defines a physical GPU whose page tables are modified, and the allocation handle (if not NULL) defines where the page table entries are pointing to. The allocation can be resident in any physical GPU memory segment.

The GPU VA range, which is allocated by the API, is freed when the allocation (the GPU VA is mapped to) is destroyed. The VA range can also be freed by calling [**D3DMTFreeGpuVirtualAddress**](../d3dkmthk/nf-d3dkmthk-d3dkmtfreegpuvirtualaddress.md), but this needs to be synchronized with allocation destruction if necessary.

## -see-also

[**DxgkCbReserveGpuVirtualAddressRange**](../d3dkmddi/nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md)
