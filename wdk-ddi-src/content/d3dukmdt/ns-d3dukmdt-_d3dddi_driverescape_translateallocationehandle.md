---
UID: NS:d3dukmdt._D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
title: _D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
author: windows-driver-content
description: Used to translate the guest allocation to the corresponding host handle.
ms.assetid: 8a286cbc-92cb-45cd-ac98-c0d185fc0bf0
ms.date: 
ms.topic: struct
ms.keywords: _D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE, D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE, 
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dukmdt.h
api_name: 
-	_D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
product:
-	Windows
targetos: Windows
tech.root: display
---

# _D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE structure

## -description

Used to translate the guest allocation to the corresponding host handle.

## -struct-fields

### -field EscapeType

A [D3DDDI_DRIVERESCAPETYPE](ne-d3dukmdt-_d3dddi_driverescapetype.md).

### -field hAllocation
 
[in] A handle to a DirectX Graphics allocation, returned from [DxgkCreateAllocation](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md).

[out] A handle, which can be sent to the kernel mode driver and used in [DxgkCbAcquireHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_acquirehandledata.md), [DxgkCbReleaseHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_releasehandledata.md), [DxgkCbGetHandleData](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata.md), and [DxgkCbGetHandleParent](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandleparent.md).

## -remarks

## -see-also
