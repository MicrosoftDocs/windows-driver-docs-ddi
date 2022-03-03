---
UID: NF:d3dkmthk.D3DKMTFreeGpuVirtualAddress
title: D3DKMTFreeGpuVirtualAddress function (d3dkmthk.h)
description: D3DKMTFreeGpuVirtualAddress releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped.
old-location: display\d3dkmtfreegpuvirtualaddress.htm
ms.date: 02/25/2022
keywords: ["D3DKMTFreeGpuVirtualAddress function"]
ms.keywords: D3DKMTFreeGpuVirtualAddress, D3DKMTFreeGpuVirtualAddress function [Display Devices], d3dkmthk/D3DKMTFreeGpuVirtualAddress, display.d3dkmtfreegpuvirtualaddress
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
 - D3DKMTFreeGpuVirtualAddress
 - d3dkmthk/D3DKMTFreeGpuVirtualAddress
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
 - D3DKMTFreeGpuVirtualAddress
---

# D3DKMTFreeGpuVirtualAddress function

## -description

**D3DKMTFreeGpuVirtualAddress** releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_FREEGPUVIRTUALADDRESS](ns-d3dkmthk-_d3dkmt_freegpuvirtualaddress.md) structure that describes the operation.

## -returns

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The device context was successfully created. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -remarks

The freed virtual address should not be accessed immediately after the call. If there are outstanding [MapGpuVirtualAddress](nf-d3dkmthk-d3dkmtmapgpuvirtualaddress.md) and [UpdateGpuVirtualAddress](nf-d3dkmthk-d3dkmtupdategpuvirtualaddress.md) operations, which reference the virtual address, they will be ignored after the virtual address is freed. A new virtual address range can be allocated in place of the freed one immediately after return from the function.

## -see-also

[D3DKMT_FREEGPUVIRTUALADDRESS](ns-d3dkmthk-_d3dkmt_freegpuvirtualaddress.md)

[MapGpuVirtualAddress](nf-d3dkmthk-d3dkmtmapgpuvirtualaddress.md)

[UpdateGpuVirtualAddress](nf-d3dkmthk-d3dkmtupdategpuvirtualaddress.md)
