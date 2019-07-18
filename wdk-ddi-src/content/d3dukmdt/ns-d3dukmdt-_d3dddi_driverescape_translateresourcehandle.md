---
UID: NS:d3dukmdt._D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
title: _D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE (d3dukmdt.h)
description: Used to translate the resource handle to the corresponding host handle.
ms.assetid: 75a6f37a-1c3e-43d0-8761-cbdab68ad6fd
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dukmdt/_D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE"
ms.keywords: _D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE, D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE, 
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dukmdt.h
api_name: 
- _D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE structure

## -description

Used to translate the resource handle to the corresponding host handle.

## -struct-fields

### -field EscapeType

A [D3DDDI_DRIVERESCAPETYPE](ne-d3dukmdt-_d3dddi_driverescapetype.md).

### -field hResource
 
[in] A handle to DirectX Graphics resource, returned from [DxgkDdiCreateAllocation](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md).

[out] A handle, which can be sent to the kernel mode driver and used in [DxgkCbAcquireHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_acquirehandledata.md), [DxgkCbReleaseHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_releasehandledata.md), [DxgCbEnumHandleChildren](../d3dkmddi/nc-d3dkmddi-dxgkcb_enumhandlechildren.md), and [DxgkCbGetHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata.md).

## -remarks

## -see-also
