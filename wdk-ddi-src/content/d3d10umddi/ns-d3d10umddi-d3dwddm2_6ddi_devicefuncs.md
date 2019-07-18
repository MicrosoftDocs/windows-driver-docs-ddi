---
UID: NS:d3d10umddi.D3DWDDM2_6DDI_DEVICEFUNCS
title: D3DWDDM2_6DDI_DEVICEFUNCS
author: windows-driver-content
description: This structure contains the user mode device function table for Windows Display Driver Model (WDDM) 2.6.
tech.root: display
ms.assetid: 80a077b6-7190-4416-a86d-992375fe8de0
ms.author: windowsdriverdev
ms.date: 04/04/19
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3DWDDM2_6DDI_DEVICEFUNCS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3DWDDM2_6DDI_DEVICEFUNCS, D3DWDDM2_6DDI_DEVICEFUNCS, 
req.header: d3d10umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DWDDM2_6DDI_DEVICEFUNCS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d10umddi.h
api_name: 
 - D3DWDDM2_6DDI_DEVICEFUNCS
product: 
 - Windows
targetos: Windows
ms.custom: WDDM 2.6, 19H1
---

# D3DWDDM2_6DDI_DEVICEFUNCS structure

## -description

This structure contains the user mode device function table for Windows Display Driver Model (WDDM) 2.6.

## -struct-fields


### -field pfnDefaultConstantBufferUpdateSubresourceUP

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">DefaultConstantBufferUpdateSubresourceUP</a> function.


### -field pfnVsSetConstantBuffers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">VsSetConstantBuffers</a> function.


### -field pfnPsSetShaderResources

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">PsSetShaderResources</a> function.


### -field pfnPsSetShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">PsSetShader</a> function.


### -field pfnPsSetSamplers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">PsSetSamplers</a> function.


### -field pfnVsSetShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">VsSetShader</a> function.


### -field pfnDrawIndexed

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawindexed">DrawIndexed</a> function.


### -field pfnDraw

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_draw">Draw</a> function.


### -field pfnDynamicIABufferMapNoOverwrite

A pointer to a PFND3D10DDI_RESOURCEMAP function.

### -field pfnDynamicIABufferUnmap

A pointer to a PFND3D10DDI_RESOURCEUNMAP function.

### -field pfnDynamicConstantBufferMapDiscard

A pointer to a PFND3D10DDI_RESOURCEMAP function.

### -field pfnDynamicIABufferMapDiscard

A pointer to a PFND3D10DDI_RESOURCEMAP function.

### -field pfnDynamicConstantBufferUnmap
 
A pointer to a PFND3D10DDI_RESOURCEUNMAP function.

### -field pfnPsSetConstantBuffers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">PsSetConstantBuffers</a> function.


### -field pfnIaSetInputLayout

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setinputlayout">IaSetInputLayout</a> function.


### -field pfnIaSetVertexBuffers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_ia_setvertexbuffers">IaSetVertexBuffers</a> function.


### -field pfnIaSetIndexBuffer

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer">IaSetIndexBuffer</a> function.


### -field pfnDrawIndexedInstanced

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced">DrawIndexedInstanced</a> function.


### -field pfnDrawInstanced

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawinstanced">DrawInstanced</a> function.


### -field pfnDynamicResourceMapDiscard

A pointer to the PFND3D10DDI_RESOURCEMAP function.

### -field pfnDynamicResourceUnmap

A pointer to the PFND3D10DDI_RESOURCEUNMAP function.


### -field pfnGsSetConstantBuffers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">GsSetConstantBuffers</a> function.


### -field pfnGsSetShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">GsSetShader</a> function.


### -field pfnIaSetTopology

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_ia_settopology">IaSetTopology</a> function.


### -field pfnStagingResourceMap

A pointer to a PFND3D10DDI_RESOURCEMAP function.


### -field pfnStagingResourceUnmap

A pointer to a PFND3D10DDI_RESOURCEUNMAP function.


### -field pfnVsSetShaderResources

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">VsSetShaderResources</a> function.


### -field pfnVsSetSamplers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">VsSetSamplers</a> function.


### -field pfnGsSetShaderResources

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">GsSetShaderResources</a> function.


### -field pfnGsSetSamplers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">GsSetSamplers</a> function.


### -field pfnSetRenderTargets

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setrendertargets">SetRenderTargets</a> function.


### -field pfnShaderResourceViewReadAfterWriteHazard

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_shaderresourceviewreadafterwritehazard">ShaderResourceViewReadAfterWriteHazard</a> function.


### -field pfnResourceReadAfterWriteHazard

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcereadafterwritehazard">ResourceReadAfterWriteHazard</a> function.


### -field pfnSetBlendState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setblendstate">SetBlendState</a> function.


### -field pfnSetDepthStencilState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setdepthstencilstate">SetDepthStencilState</a> function.


### -field pfnSetRasterizerState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setrasterizerstate">SetRasterizerState</a> function.


### -field pfnQueryEnd

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_queryend">QueryEnd</a> function.


### -field pfnQueryBegin

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querybegin">QueryBegin</a> function.


### -field pfnResourceCopyRegion

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion">ResourceCopyRegion</a> function.


### -field pfnResourceUpdateSubresourceUP

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">ResourceUpdateSubresourceUP</a> function.


### -field pfnSoSetTargets

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_so_settargets">SoSetTargets</a> function.


### -field pfnDrawAuto

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawauto">DrawAuto</a> function.


### -field pfnSetViewports

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setviewports">SetViewports</a> function.


### -field pfnSetScissorRects

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setscissorrects">SetScissorRects</a> function.


### -field pfnClearRenderTargetView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_clearrendertargetview">ClearRenderTargetView</a> function.


### -field pfnClearDepthStencilView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_cleardepthstencilview">ClearDepthStencilView</a> function.


### -field pfnSetPredication

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setpredication">SetPredication</a> function.


### -field pfnQueryGetData

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a> function.


### -field pfnFlush

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a> function.


### -field pfnGenMips

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_genmips">GenMips</a> function.


### -field pfnResourceCopy

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy">ResourceCopy</a> function.


### -field pfnResourceResolveSubresource

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceresolvesubresource">ResourceResolveSubresource</a> function.


### -field pfnResourceMap

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function.


### -field pfnResourceUnmap

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a> function.


### -field pfnResourceIsStagingBusy

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy">ResourceIsStagingBusy</a> function.


### -field pfnRelocateDeviceFuncs

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_relocatedevicefuncs">RelocateDeviceFuncs</a> function.


### -field pfnCalcPrivateResourceSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateresourcesize">CalcPrivateResourceSize</a> function.


### -field pfnCalcPrivateOpenedResourceSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateopenedresourcesize">CalcPrivateOpenedResourceSize</a> function.


### -field pfnCreateResource

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a> function.


### -field pfnOpenResource

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_openresource">OpenResource</a> function.


### -field pfnDestroyResource

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyresource">DestroyResource</a> function.


### -field pfnCalcPrivateShaderResourceViewSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize</a> function.


### -field pfnCreateShaderResourceView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview">CreateShaderResourceView</a> function.


### -field pfnDestroyShaderResourceView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview">DestroyShaderResourceView</a> function.


### -field pfnCalcPrivateRenderTargetViewSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize">CalcPrivateRenderTargetViewSize</a> function.


### -field pfnCreateRenderTargetView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a> function.


### -field pfnDestroyRenderTargetView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview">DestroyRenderTargetView</a> function.


### -field pfnCalcPrivateDepthStencilViewSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize">CalcPrivateDepthStencilViewSize</a> function.


### -field pfnCreateDepthStencilView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview">CreateDepthStencilView</a> function.


### -field pfnDestroyDepthStencilView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview">DestroyDepthStencilView</a> function.


### -field pfnCalcPrivateElementLayoutSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize">CalcPrivateElementLayoutSize</a> function.


### -field pfnCreateElementLayout

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createelementlayout">CreateElementLayout</a> function.


### -field pfnDestroyElementLayout

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout">DestroyElementLayout</a> function.


### -field pfnCalcPrivateBlendStateSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateblendstatesize">CalcPrivateBlendStateSize</a> function.


### -field pfnCreateBlendState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createblendstate">CreateBlendState</a> function.


### -field pfnDestroyBlendState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyblendstate">DestroyBlendState</a> function.


### -field pfnCalcPrivateDepthStencilStateSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize">CalcPrivateDepthStencilStateSize</a> function.


### -field pfnCreateDepthStencilState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate">CreateDepthStencilState</a> function.


### -field pfnDestroyDepthStencilState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilstate">DestroyDepthStencilState</a> function.


### -field pfnCalcPrivateRasterizerStateSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterasterizerstatesize">CalcPrivateRasterizerStateSize</a> function.


### -field pfnCreateRasterizerState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrasterizerstate">CreateRasterizerState</a> function.


### -field pfnDestroyRasterizerState

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate">DestroyRasterizerState</a> function.


### -field pfnCalcPrivateShaderSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize">CalcPrivateShaderSize</a> function.


### -field pfnCreateVertexShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvertexshader">CreateVertexShader</a> function.


### -field pfnCreateGeometryShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_creategeometryshader">CreateGeometryShader</a> function.


### -field pfnCreatePixelShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createpixelshader">CreatePixelShader</a> function.


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput">CalcPrivateGeometryShaderWithStreamOutput</a> function.


### -field pfnCreateGeometryShaderWithStreamOutput

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_creategeometryshaderwithstreamoutput">CreateGeometryShaderWithStreamOutput</a> function.


### -field pfnDestroyShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a> function.


### -field pfnCalcPrivateSamplerSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize">CalcPrivateSamplerSize</a> function.


### -field pfnCreateSampler

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createsampler">CreateSampler</a> function.


### -field pfnDestroySampler

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroysampler">DestroySampler</a> function.


### -field pfnCalcPrivateQuerySize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatequerysize">CalcPrivateQuerySize</a> function.


### -field pfnCreateQuery

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createquery">CreateQuery</a> function.


### -field pfnDestroyQuery

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyquery">DestroyQuery</a> function.


### -field pfnCheckFormatSupport

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkformatsupport">CheckFormatSupport</a> function.


### -field pfnCheckMultisampleQualityLevels

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels">CheckMultisampleQualityLevels</a> function.


### -field pfnCheckCounterInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo">CheckCounterInfo</a> function.


### -field pfnCheckCounter

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkcounter">CheckCounter</a> function.


### -field pfnDestroyDevice

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_destroydevice">DestroyDevice</a> function.


### -field pfnSetTextFilterSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_settextfiltersize">SetTextFilterSize</a> function.


### -field pfnResourceConvert

A pointer to the PFND3D10DDI_RESOURCECOPY function.

### -field pfnResourceConvertRegion

A pointer to the PFND3D11_1DDI_RESOURCECOPYREGION function.

### -field pfnResetPrimitiveID

A pointer to the PFND3D10DDI_RESETPRIMITIVEID function.

### -field pfnSetVertexPipelineOutput

A pointer to the PFND3D10DDI_SETVERTEXPIPELINEOUTPUT function.

### -field pfnDrawIndexedInstancedIndirect

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_drawindexedinstancedindirect">DrawIndexedInstancedIndirect</a> function.


### -field pfnDrawInstancedIndirect

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_drawinstancedindirect">DrawInstancedIndirect</a> function.


### -field pfnCommandListExecute

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_commandlistexecute">CommandListExecute</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnHsSetShaderResources

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">HsSetShaderResources</a> function.


### -field pfnHsSetShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">HsSetShader</a> function.


### -field pfnHsSetSamplers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">HsSetSamplers</a> function.


### -field pfnHsSetConstantBuffers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">HsSetConstantBuffers</a> function.


### -field pfnDsSetShaderResources

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">DsSetShaderResources</a> function.


### -field pfnDsSetShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">DsSetShader</a> function.


### -field pfnDsSetSamplers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">DsSetSamplers</a> function.


### -field pfnDsSetConstantBuffers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">DsSetConstantBuffers</a> function.


### -field pfnCreateHullShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createhullshader">CreateHullShader</a> function.


### -field pfnCreateDomainShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createdomainshader">CreateDomainShader</a> function.


### -field pfnCheckDeferredContextHandleSizes

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes">CheckDeferredContextHandleSizes</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnCalcDeferredContextHandleSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcdeferredcontexthandlesize">CalcDeferredContextHandleSize</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnCalcPrivateDeferredContextSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatedeferredcontextsize">CalcPrivateDeferredContextSize</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnCreateDeferredContext

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createdeferredcontext">CreateDeferredContext</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnAbandonCommandList

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist">AbandonCommandList</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnCalcPrivateCommandListSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize">CalcPrivateCommandListSize</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnCreateCommandList

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createcommandlist">CreateCommandList</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnDestroyCommandList

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_destroycommandlist">DestroyCommandList</a> function.

Only required when supporting D3D11DDICAPS_COMMANDLISTS.

### -field pfnCalcPrivateTessellationShaderSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize">CalcPrivateTessellationShaderSize</a> function.


### -field pfnPsSetShaderWithIfaces

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">PsSetShaderWithIfaces</a> function.


### -field pfnVsSetShaderWithIfaces

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">VsSetShaderWithIfaces</a> function.


### -field pfnGsSetShaderWithIfaces

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">GsSetShaderWithIfaces</a> function.


### -field pfnHsSetShaderWithIfaces

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">HsSetShaderWithIfaces</a> function.


### -field pfnDsSetShaderWithIfaces

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">DsSetShaderWithIfaces</a> function.


### -field pfnCsSetShaderWithIfaces

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">CsSetShaderWithIfaces</a> function.


### -field pfnCreateComputeShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createcomputeshader">CreateComputeShader</a> function.


### -field pfnCsSetShader

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">CsSetShader</a> function.


### -field pfnCsSetShaderResources

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">CsSetShaderResources</a> function.


### -field pfnCsSetSamplers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">CsSetSamplers</a> function.


### -field pfnCsSetConstantBuffers

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">CsSetConstantBuffers</a> function.


### -field pfnCalcPrivateUnorderedAccessViewSize

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize">CalcPrivateUnorderedAccessViewSize</a> function.


### -field pfnCreateUnorderedAccessView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a> function.


### -field pfnDestroyUnorderedAccessView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview">DestroyUnorderedAccessView</a> function.


### -field pfnClearUnorderedAccessViewUint

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewuint">ClearUnorderedAccessViewUint</a> function.


### -field pfnClearUnorderedAccessViewFloat

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewfloat">ClearUnorderedAccessViewFloat</a> function.


### -field pfnCsSetUnorderedAccessViews

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setunorderedaccessviews">CsSetUnorderedAccessViews</a> function.


### -field pfnDispatch

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_dispatch">Dispatch</a> function.


### -field pfnDispatchIndirect

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_dispatchindirect">DispatchIndirect</a> function.


### -field pfnSetResourceMinLOD

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setresourceminlod">SetResourceMinLOD</a> function.


### -field pfnCopyStructureCount

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_copystructurecount">CopyStructureCount</a> function.


### -field pfnRecycleCommandList

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_recyclecommandlist">RecycleCommandList</a> function.


### -field pfnRecycleCreateCommandList

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_recyclecreatecommandlist">RecycleCreateCommandList</a> function.


### -field pfnRecycleCreateDeferredContext

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_recyclecreatedeferredcontext">RecycleCreateDeferredContext</a> function.


### -field pfnRecycleDestroyCommandList

 
A pointer to the PFND3D11DDI_DESTROYCOMMANDLIST function.

### -field pfnDiscard

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_discard">Discard</a> function.


### -field pfnAssignDebugBinary

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_assigndebugbinary">AssignDebugBinary</a> function.


### -field pfnDynamicConstantBufferMapNoOverwrite

A pointer to the PFND3D10DDI_RESOURCEMAP function.


### -field pfnCheckDirectFlipSupport

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_checkdirectflipsupport">CheckDirectFlipSupport</a> function.


### -field pfnClearView

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_clearview">ClearView</a> function.


### -field pfnUpdateTileMappings

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_updatetilemappings">UpdateTileMappings</a> function.


### -field pfnCopyTileMappings

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_copytilemappings">CopyTileMappings</a> function.


### -field pfnCopyTiles

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_copytiles">CopyTiles</a> function.


### -field pfnUpdateTiles

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_updatetiles">UpdateTiles</a> function.


### -field pfnTiledResourceBarrier

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_tiledresourcebarrier">TiledResourceBarrier</a> function.


### -field pfnGetMipPacking

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_getmippacking">GetMipPacking</a> function.


### -field pfnResizeTilePool

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_resizetilepool">ResizeTilePool</a> function.


### -field pfnSetMarker

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_setmarker">SetMarker</a> function.


### -field pfnSetMarkerMode

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm1_3ddi_setmarkermode">SetMarkerMode</a> function.


### -field pfnSetHardwareProtection

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_sethardwareprotection">SetHardwareProtection</a> function.

Available starting in WDDM 2.0.

### -field pfnGetResourceLayout

A pointer to the PFND3DWDDM2_0DDI_GETRESOURCELAYOUT function.

Available starting in WDDM 2.0.
 
### -field pfnRetrieveShaderComment

A pointer to the PFND3DWDDM2_0DDI_RETRIEVE_SHADER_COMMENT function.

Available starting in WDDM 2.0.

### -field pfnSetHardwareProtectionState

A pointer to the PFND3DWDDM2_0DDI_SETHARDWAREPROTECTIONSTATE function.

Available starting in WDDM 2.0.

### -field pfnAcquireResource

A pointer to the PFND3DWDDM2_1DDI_SYNC_TOKEN function.

Available starting in WDDM 2.1.

### -field pfnReleaseResource

A pointer to the PFND3DWDDM2_1DDI_SYNC_TOKEN function.

Available starting in WDDM 2.1.

### -field pfnCalcPrivateShaderCacheSessionSize

A pointer to the PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE function.

Available starting in WDDM 2.2.

### -field pfnCreateShaderCacheSession

A pointer to the PFND3DWDDM2_2DDI_CREATE_SHADERCACHE_SESSION function.

Available starting in WDDM 2.2.

### -field pfnDestroyShaderCacheSession

A pointer to the PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION function.

Available starting in WDDM 2.2.

### -field pfnSetShaderCacheSession

A pointer to the PFND3DWDDM2_2DDI_SET_SHADERCACHE_SESSION function.

Available starting in WDDM 2.2.

### -field pfnQueryScanoutCaps

A pointer to the [PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS](nc-d3d10umddi-pfnd3dwddm2_6ddi_query_scanout_caps.md) function.

Available starting in WDDM 2.6.

### -field pfnPrepareScanoutTransformation

A pointer to the [PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION](nc-d3d10umddi-pfnd3dwddm2_6ddi_prepare_scanout_transformation.md) function.

Available starting in WDDM 2.6.

## -remarks

## -see-also
