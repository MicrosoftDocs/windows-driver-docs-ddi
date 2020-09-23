---
UID: NS:d3d12umddi.D3D12DDIARG_OPENADAPTER
title: D3D12DDIARG_OPENADAPTER (d3d12umddi.h)
description: The D3D12DDIARG_OPENADAPTER structure describes the graphics adapter object.
old-location: display\d3d12ddiarg_openadapter.htm
ms.assetid: 1FABEEBC-358C-40EB-8F5C-F834EE57A1A8
ms.date: 05/10/2018
keywords: ["D3D12DDIARG_OPENADAPTER structure"]
ms.keywords: D3D12DDIARG_OPENADAPTER, D3D12DDIARG_OPENADAPTER structure [Display Devices], d3d12umddi/D3D12DDIARG_OPENADAPTER, display.d3d12ddiarg_openadapter
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
tech.root: display
req.typenames: D3D12DDIARG_OPENADAPTER
f1_keywords:
 - D3D12DDIARG_OPENADAPTER
 - d3d12umddi/D3D12DDIARG_OPENADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_OPENADAPTER
---

# D3D12DDIARG_OPENADAPTER structure


## -description

The D3D12DDIARG_OPENADAPTER structure describes the graphics adapter object.

## -struct-fields

### -field hRTAdapter

[in] A runtime handle to the graphics adapter object that specifies the handle that the driver should use to query for graphics adapter capabilities when the driver calls the Microsoft Direct3D runtime-supplied <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> callback function.

### -field hAdapter

[out] A handle to the graphics adapter object that specifies the handle that the Direct3D runtime uses in subsequent driver calls to identify the graphics adapter object. The driver generates a unique handle and passes it back to the Direct3D runtime.

### -field pAdapterCallbacks

[in] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a> structure that contains the Direct3D runtime-supplied <b>pfnQueryAdapterInfoCb</b> callback function that the driver can use.

### -field pAdapterFuncs

[out] A pointer to a D3D12DDI_ADAPTERFUNCS structure that contains a table of user-mode display driver adapter-specific functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver about operations that are specific to the graphics adapter.