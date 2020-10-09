---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATERASTERIZERSTATE
title: PFND3D11_1DDI_CREATERASTERIZERSTATE (d3d10umddi.h)
description: Creates a rasterizer state.
old-location: display\createrasterizerstate_d3d11_1_.htm
ms.assetid: 5640e1c9-6a38-4eca-9048-0bc9ff66c43c
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CREATERASTERIZERSTATE callback function"]
ms.keywords: CreateRasterizerState(D3D11_1), CreateRasterizerState(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CREATERASTERIZERSTATE, PFND3D11_1DDI_CREATERASTERIZERSTATE callback, d3d10umddi/CreateRasterizerState(D3D11_1), display.createrasterizerstate_d3d11_1_, display.pfncreaterasterizerstate
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_CREATERASTERIZERSTATE
 - d3d10umddi/PFND3D11_1DDI_CREATERASTERIZERSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CreateRasterizerState(D3D11_1)
product:
 - Windows
---

# PFND3D11_1DDI_CREATERASTERIZERSTATE callback function


## -description

Creates a rasterizer state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pRasterizerDesc* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc">D3D11_1_DDI_RASTERIZER_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a rasterizer state.

### -param Arg3

*hRasterizerState* [in]

A handle to the driver's private data for the rasterizer state.

### -param Arg4

*hRTRasterizerState*

A handle to the rasterizer state that the driver should use when it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is incorrect; therefore, the runtime will not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate">DestroyRasterizerState</a> function to destroy the handle that the <i>hRasterizerState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of rasterizer-state objects on a device at a time.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivaterasterizerstatesize">CalcPrivateRasterizerStateSize(D3D11_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc">D3D11_1_DDI_RASTERIZER_DESC</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate">DestroyRasterizerState</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>