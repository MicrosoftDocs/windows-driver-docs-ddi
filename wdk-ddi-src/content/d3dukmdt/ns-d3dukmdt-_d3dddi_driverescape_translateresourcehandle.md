---
UID: NS:d3dukmdt._D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
title: D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE (d3dukmdt.h)
description: Used to translate the resource handle to the corresponding host handle.
ms.date: 09/12/2022
keywords: ["D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE structure"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
 - d3dukmdt/_D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
 - D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
 - d3dukmdt/D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
 - D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE
dev_langs:
 - c++
---

# D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE structure

## -description

The **D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE** structure is used to translate the resource handle to the corresponding host handle.

## -struct-fields

### -field EscapeType

A [**D3DDDI_DRIVERESCAPETYPE**](ne-d3dukmdt-_d3dddi_driverescapetype.md). Must be set to **D3DDDI_DRIVERESCAPETYPE_TRANSLATERESOURCEHANDLE**.

### -field hResource

[in/out] On entry, a handle to a DirectX graphics resource that was returned from [**DXGKDDI_CREATEALLOCATION**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md).

On return, a handle  that can be sent to the kernel-mode driver and used in functions such as [**DXGKCB_ACQUIREHANDLEDATA**](../d3dkmddi/nc-d3dkmddi-dxgkcb_acquirehandledata.md), [**DXGKCB_RELEASEHANDLEDATA**](../d3dkmddi/nc-d3dkmddi-dxgkcb_releasehandledata.md), [**DXGKCB_GETHANDLEDATA**](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata.md), and [**DXGKCB_GETHANDLEPARENT**](../d3dkmddi/nc-d3dkmddi-dxgkcb_gethandleparent.md).

## -remarks

The **D3DDDI_DRIVERESCAPE_TRANSLATERESOURCEHANDLE** structure is used with the **D3DDDI_DRIVERESCAPETYPE_TRANSLATERESOURCEHANDLE** known escape type.

## -see-also

[**D3DDDI_DRIVERESCAPETYPE**](ne-d3dukmdt-_d3dddi_driverescapetype.md)

[**DXGKARG_ESCAPE**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_escape.md)

[**DXGKDDI_ESCAPE**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md)
