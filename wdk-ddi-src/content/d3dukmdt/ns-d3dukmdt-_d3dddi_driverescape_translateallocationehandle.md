---
UID: NS:d3dukmdt._D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
title: D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE (d3dukmdt.h)
description: Used to translate the guest allocation to the corresponding host handle.
ms.date: 09/12/2022
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
 - D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE
dev_langs:
 - c++
---

# D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE structure

## -description

The **D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE** structure is used to translate the guest allocation to the corresponding host handle.

## -struct-fields

### -field EscapeType

[in] A [**D3DDDI_DRIVERESCAPETYPE**](ne-d3dukmdt-_d3dddi_driverescapetype.md). Must be set to **D3DDDI_DRIVERESCAPETYPE_TRANSLATEALLOCATIONHANDLE**.

### -field hAllocation

[in/out] On entry, a handle to a DirectX graphics allocation that was returned from [**DXGKDDI_CREATEALLOCATION**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md).

On return, a handle that can be sent to the kernel-mode driver and used in functions such as [**DXGKCB_ACQUIREHANDLEDATA**](../d3dkmddi/nc-d3dkmddi-dxgkcb_acquirehandledata.md), [**DXGKCB_RELEASEHANDLEDATA**](../d3dkmddi/nc-d3dkmddi-dxgkcb_releasehandledata.md), [**DXGKCB_GETHANDLEDATA**](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata.md), and [**DXGKCB_GETHANDLEPARENT**](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandleparent.md).

## -remarks

The **D3DDDI_DRIVERESCAPE_TRANSLATEALLOCATIONEHANDLE** structure is used with the **D3DDDI_DRIVERESCAPETYPE_TRANSLATEALLOCATIONHANDLE** known escape type.

## -see-also

[**D3DDDI_DRIVERESCAPETYPE**](ne-d3dukmdt-_d3dddi_driverescapetype.md)

[**DXGKARG_ESCAPE**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_escape.md)

[**DXGKDDI_ESCAPE**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md)
