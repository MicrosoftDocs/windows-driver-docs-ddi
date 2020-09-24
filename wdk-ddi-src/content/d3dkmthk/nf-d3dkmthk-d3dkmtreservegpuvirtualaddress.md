---
UID: NF:d3dkmthk.D3DKMTReserveGpuVirtualAddress
title: D3DKMTReserveGpuVirtualAddress function (d3dkmthk.h)
description: D3DKMTReserveGpuVirtualAddress reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.
old-location: display\d3dkmtreservegpuvirtualaddress.htm
ms.assetid: 2F8B689C-162C-4C1B-BD45-A154079334D0
ms.date: 05/10/2018
keywords: ["D3DKMTReserveGpuVirtualAddress function"]
ms.keywords: D3DKMTReserveGpuVirtualAddress, D3DKMTReserveGpuVirtualAddress function [Display Devices], d3dkmthk/D3DKMTReserveGpuVirtualAddress, display.d3dkmtreservegpuvirtualaddress
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
 - D3DKMTReserveGpuVirtualAddress
 - d3dkmthk/D3DKMTReserveGpuVirtualAddress
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
 - D3DKMTReserveGpuVirtualAddress
---

# D3DKMTReserveGpuVirtualAddress function


## -description

<b>D3DKMTReserveGpuVirtualAddress</b> reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.

The driver may choose the base GPU virtual address to use for the reservation by specifying a non-NULL value for <b>BaseAddress</b>. The video memory manager will use the specified range if it is available. If the range intersects with an existing range, the operation will fail. The driver may pass a <b>NULL</b> value in the <b>BaseAddress</b> member to let the video memory manager pick a base address.

When the driver chooses to let the video memory manager pick a base address for the GPU virtual address range, it may choose to constrain the range that the video memory manager will consider by specifying non-NULL values for <b>MinimumAddress</b> and <b>MaximumAddress</b>. The video memory manager will ensure that the allocated GPU virtual address range is entirely contained in the range. The driver may specify only a <b>MinimumAddress</b> and the driver will infer the <b>MaximumAddress</b> is the end of the address space. If  only a <b>MaximumAddress</b>  is specified, the <b>MinimumAddress</b> is inferred to be 0.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_reservegpuvirtualaddress">D3DDDI_RESERVEGPUVIRTUALADDRESS</a> structure that describes the operation.

## -returns

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully created.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.