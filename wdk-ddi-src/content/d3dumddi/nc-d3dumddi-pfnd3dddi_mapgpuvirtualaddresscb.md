---
UID: NC:d3dumddi.PFND3DDDI_MAPGPUVIRTUALADDRESSCB
title: PFND3DDDI_MAPGPUVIRTUALADDRESSCB (d3dumddi.h)
description: Learn more about the pfnMapGpuVirtualAddressCb function.
tech.root: display
ms.date: 07/25/2023
keywords: ["PFND3DDDI_MAPGPUVIRTUALADDRESSCB callback function"]
ms.keywords: PFND3DDDI_MAPGPUVIRTUALADDRESSCB, PFND3DDDI_MAPGPUVIRTUALADDRESSCB callback, d3dumddi/pfnMapGpuVirtualAddressCb, display.pfnmapgpuvirtualaddresscb, pfnMapGpuVirtualAddressCb, pfnMapGpuVirtualAddressCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_MAPGPUVIRTUALADDRESSCB
 - d3dumddi/PFND3DDDI_MAPGPUVIRTUALADDRESSCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_MAPGPUVIRTUALADDRESSCB
---

# PFND3DDDI_MAPGPUVIRTUALADDRESSCB callback function

## -description

**pfnMapGpuVirtualAddressCb** maps GPU virtual address (VA) ranges to a specific allocation range or puts it to the [*Invalid* or *Zero*](../d3dukmdt/ns-d3dukmdt-_d3dddigpuvirtualaddress_protection_type.md) state.

## -parameters

### -param hDevice

A handle to the display device.

### -param unnamedParam2

[in/out] **pDate** is a pointer to a [**D3DDDI_MAPGPUVIRTUALADDRESS**](../d3dukmdt/ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md) structure that describes the operation to perform.

## -returns

**pfnMapGpuVirtualAddressCb** returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The operation completed successfully.|
|E_PENDING|The call was successful, but the operation is not finished. The caller must wait for the returned fence value before accessing the allocation.|

This function might also return other values.

## -remarks

The user-mode driver can specify a base GPU virtual address (VA) to map or let the video memory manager automatically pick one. When specifying a non-NULL **BaseAddress** value, the entire range from **BaseAddress** to **BaseAddress**+**Size** must be in a freed state or belong to a VA range that was obtained by calling **pfnMapGpuVirtualAddressCb** or [**pfnReserveGpuVirtualAddressCb**](nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md). When **Protection.Zero** or **Protection.NoAccess** is specified, the VA range can't belong to a range that was obtained by calling **pfnMapGpuVirtualAddressCb**.

The user-mode driver can specify whether the mapping should allow for write and execute privileges in addition to read privileges, which always exist by default.

In linked display adapter (LDA) configuration, the paging queue defines a physical GPU whose page tables are modified, and the allocation handle (if not NULL) defines where the page table entries are pointing to. The allocation can be resident in any physical GPU memory segment.

The GPU VA range, which is allocated by the API, is freed when the allocation (the GPU VA is mapped to) is destroyed. The VA range can also be freed by calling [**PFND3DDDI_FREEGPUVIRTUALADDRESSCB**](nc-d3dumddi-pfnd3dddi_freegpuvirtualaddresscb.md), but this needs to be synchronized with allocation destruction if necessary.

## -see-also

[**D3DDDI_MAPGPUVIRTUALADDRESS**](../d3dukmdt/ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md)

[**pfnReserveGpuVirtualAddressCb**](nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md)
