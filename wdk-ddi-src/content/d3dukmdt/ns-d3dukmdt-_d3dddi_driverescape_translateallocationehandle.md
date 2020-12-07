---
UID: NS:d3dukmdt._D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
title: _D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE (d3dukmdt.h)
description: Used to translate the guest allocation to the corresponding host handle.
ms.date: 10/19/2018
keywords: ["D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE structure"]
ms.keywords: _D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE, D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE,
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
req.typenames: D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
 - d3dukmdt/_D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
 - D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
 - d3dukmdt/D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
dev_langs:
 - c++
---

# _D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE structure


## -description

Used to translate the guest allocation to the corresponding host handle.

## -struct-fields

### -field hAllocation

 
[in] A handle to a DirectX Graphics allocation, returned from [DxgkCreateAllocation](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md).

[out] A handle, which can be sent to the kernel mode driver and used in [DxgkCbAcquireHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_acquirehandledata.md), [DxgkCbReleaseHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_releasehandledata.md), [DxgkCbGetHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata.md), and [DxgkCbGetHandleParent](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandleparent.md).

### -field EscapeType

A [D3DDDI_DRIVERESCAPETYPE](ne-d3dukmdt-_d3dddi_driverescapetype.md).

## -remarks

## -see-also

