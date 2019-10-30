---
UID: NS:d3d10umddi.D3D11DDI_DEVICEFUNCS
title: D3D11DDI_DEVICEFUNCS (d3d10umddi.h)
description: The D3D11DDI_DEVICEFUNCS structure contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 11 runtime can implement to render graphics primitives and process state changes.
old-location: display\d3d11ddi_devicefuncs.htm
ms.assetid: fabd77b9-2a2e-4995-a99f-50b46806e312
ms.date: 05/10/2018
ms.keywords: D3D11DDI_DEVICEFUNCS, D3D11DDI_DEVICEFUNCS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_f91ec9c6-5d1b-49ab-8a92-21028de8e10b.xml, d3d10umddi/D3D11DDI_DEVICEFUNCS, display.d3d11ddi_devicefuncs
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D11DDI_DEVICEFUNCS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_DEVICEFUNCS is supported beginning with the Windows 7 operating system.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D11DDI_DEVICEFUNCS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDI_DEVICEFUNCS
---

# D3D11DDI_DEVICEFUNCS structure


## -description


The D3D11DDI_DEVICEFUNCS structure contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 11 runtime can implement to render graphics primitives and process state changes.


## -struct-fields




### -field pfnDefaultConstantBufferUpdateSubresourceUP

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">DefaultConstantBufferUpdateSubresourceUP</a> function.


### -field pfnVsSetConstantBuffers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">VsSetConstantBuffers</a> function.


### -field pfnPsSetShaderResources

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">PsSetShaderResources</a> function.


### -field pfnPsSetShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">PsSetShader</a> function. 


### -field pfnPsSetSamplers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">PsSetSamplers</a> function.


### -field pfnVsSetShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">VsSetShader</a> function.


### -field pfnDrawIndexed

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawindexed">DrawIndexed</a> function.


### -field pfnDraw

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_draw">Draw</a> function.


### -field pfnDynamicIABufferMapNoOverwrite

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicIABufferMapNoOverwrite</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicIABufferUnmap

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicIABufferUnmap</b> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a>. 


### -field pfnDynamicConstantBufferMapDiscard

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicConstantBufferMapDiscard</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicIABufferMapDiscard

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicIABufferMapDiscard</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicConstantBufferUnmap

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicConstantBufferUnmap</b> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a>. 


### -field pfnPsSetConstantBuffers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">PsSetConstantBuffers</a> function.


### -field pfnIaSetInputLayout

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setinputlayout">IaSetInputLayout</a> function.


### -field pfnIaSetVertexBuffers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_ia_setvertexbuffers">IaSetVertexBuffers</a> function.


### -field pfnIaSetIndexBuffer

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer">IaSetIndexBuffer</a> function.


### -field pfnDrawIndexedInstanced

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced">DrawIndexedInstanced</a> function.


### -field pfnDrawInstanced

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawinstanced">DrawInstanced</a> function.


### -field pfnDynamicResourceMapDiscard

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicResourceMapDiscard</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicResourceUnmap

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicResourceUnmap</b> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a>. 


### -field pfnGsSetConstantBuffers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">GsSetConstantBuffers</a> function.


### -field pfnGsSetShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">GsSetShader</a> function.


### -field pfnIaSetTopology

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_ia_settopology">IaSetTopology</a> function.


### -field pfnStagingResourceMap

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function. For more information about whether to implement a separate <b>StagingResourceMap</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnStagingResourceUnmap

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a> function. For more information about whether to implement a separate <b>StagingResourceUnmap</b> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a>. 


### -field pfnVsSetShaderResources

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">VsSetShaderResources</a> function.


### -field pfnVsSetSamplers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">VsSetSamplers</a> function.


### -field pfnGsSetShaderResources

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">GsSetShaderResources</a> function.


### -field pfnGsSetSamplers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">GsSetSamplers</a> function.


### -field pfnSetRenderTargets

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setrendertargets">SetRenderTargets(D3D11)</a> function.


### -field pfnShaderResourceViewReadAfterWriteHazard

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_shaderresourceviewreadafterwritehazard">ShaderResourceViewReadAfterWriteHazard</a> function.


### -field pfnResourceReadAfterWriteHazard

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcereadafterwritehazard">ResourceReadAfterWriteHazard</a> function.


### -field pfnSetBlendState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setblendstate">SetBlendState</a> function.


### -field pfnSetDepthStencilState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setdepthstencilstate">SetDepthStencilState</a> function.


### -field pfnSetRasterizerState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setrasterizerstate">SetRasterizerState</a> function.


### -field pfnQueryEnd

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_queryend">QueryEnd</a> function.


### -field pfnQueryBegin

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querybegin">QueryBegin</a> function.


### -field pfnResourceCopyRegion

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion">ResourceCopyRegion</a> function.


### -field pfnResourceUpdateSubresourceUP

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">ResourceUpdateSubresourceUP</a> function.


### -field pfnSoSetTargets

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_so_settargets">SoSetTargets</a> function.


### -field pfnDrawAuto

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_drawauto">DrawAuto</a> function.


### -field pfnSetViewports

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setviewports">SetViewports</a> function.


### -field pfnSetScissorRects

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setscissorrects">SetScissorRects</a> function.


### -field pfnClearRenderTargetView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_clearrendertargetview">ClearRenderTargetView</a> function.


### -field pfnClearDepthStencilView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_cleardepthstencilview">ClearDepthStencilView</a> function.


### -field pfnSetPredication

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setpredication">SetPredication</a> function.


### -field pfnQueryGetData

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a> function.


### -field pfnFlush

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_flush">Flush(D3D10)</a> function.


### -field pfnGenMips

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_genmips">GenMips</a> function.


### -field pfnResourceCopy

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy">ResourceCopy</a> function.


### -field pfnResourceResolveSubresource

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceresolvesubresource">ResourceResolveSubresource</a> function.


### -field pfnResourceMap

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function.


### -field pfnResourceUnmap

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceunmap">ResourceUnmap</a> function.


### -field pfnResourceIsStagingBusy

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy">ResourceIsStagingBusy</a> function.


### -field pfnRelocateDeviceFuncs

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_relocatedevicefuncs">RelocateDeviceFuncs(D3D11)</a> function.


### -field pfnCalcPrivateResourceSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateresourcesize">CalcPrivateResourceSize(D3D11)</a> function.


### -field pfnCalcPrivateOpenedResourceSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateopenedresourcesize">CalcPrivateOpenedResourceSize</a> function.


### -field pfnCreateResource

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> function.


### -field pfnOpenResource

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_openresource">OpenResource(D3D10)</a> function.


### -field pfnDestroyResource

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyresource">DestroyResource(D3D10)</a> function.


### -field pfnCalcPrivateShaderResourceViewSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize(D3D11)</a> function.


### -field pfnCreateShaderResourceView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview">CreateShaderResourceView(D3D11)</a> function.


### -field pfnDestroyShaderResourceView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview">DestroyShaderResourceView</a> function.


### -field pfnCalcPrivateRenderTargetViewSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize">CalcPrivateRenderTargetViewSize</a> function.


### -field pfnCreateRenderTargetView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrendertargetview">CreateRenderTargetView</a> function.


### -field pfnDestroyRenderTargetView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview">DestroyRenderTargetView</a> function.


### -field pfnCalcPrivateDepthStencilViewSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatedepthstencilviewsize">CalcPrivateDepthStencilViewSize(D3D11)</a> function.


### -field pfnCreateDepthStencilView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createdepthstencilview">CreateDepthStencilView(D3D11)</a> function.


### -field pfnDestroyDepthStencilView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview">DestroyDepthStencilView</a> function.


### -field pfnCalcPrivateElementLayoutSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize">CalcPrivateElementLayoutSize</a> function.


### -field pfnCreateElementLayout

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createelementlayout">CreateElementLayout</a> function.


### -field pfnDestroyElementLayout

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout">DestroyElementLayout</a> function.


### -field pfnCalcPrivateBlendStateSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize">CalcPrivateBlendStateSize(D3D10_1)</a> function.


### -field pfnCreateBlendState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_createblendstate">CreateBlendState(D3D10_1)</a> function.


### -field pfnDestroyBlendState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyblendstate">DestroyBlendState</a> function.


### -field pfnCalcPrivateDepthStencilStateSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize">CalcPrivateDepthStencilStateSize</a> function.


### -field pfnCreateDepthStencilState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate">CreateDepthStencilState</a> function.


### -field pfnDestroyDepthStencilState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilstate">DestroyDepthStencilState</a> function.


### -field pfnCalcPrivateRasterizerStateSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterasterizerstatesize">CalcPrivateRasterizerStateSize</a> function.


### -field pfnCreateRasterizerState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createrasterizerstate">CreateRasterizerState</a> function.


### -field pfnDestroyRasterizerState

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate">DestroyRasterizerState</a> function.


### -field pfnCalcPrivateShaderSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize">CalcPrivateShaderSize</a> function.


### -field pfnCreateVertexShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createvertexshader">CreateVertexShader(D3D10)</a> function.


### -field pfnCreateGeometryShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_creategeometryshader">CreateGeometryShader</a> function.


### -field pfnCreatePixelShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createpixelshader">CreatePixelShader(D3D10)</a> function.


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivategeometryshaderwithstreamoutput">CalcPrivateGeometryShaderWithStreamOutput(D3D11)</a> function. 


### -field pfnCreateGeometryShaderWithStreamOutput

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_creategeometryshaderwithstreamoutput">CreateGeometryShaderWithStreamOutput(D3D11)</a> function.


### -field pfnDestroyShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a> function.


### -field pfnCalcPrivateSamplerSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize">CalcPrivateSamplerSize</a> function.


### -field pfnCreateSampler

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createsampler">CreateSampler</a> function.


### -field pfnDestroySampler

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroysampler">DestroySampler</a> function.


### -field pfnCalcPrivateQuerySize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatequerysize">CalcPrivateQuerySize</a> function.


### -field pfnCreateQuery

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a> function.


### -field pfnDestroyQuery

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyquery">DestroyQuery(D3D10)</a> function.


### -field pfnCheckFormatSupport

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkformatsupport">CheckFormatSupport</a> function.


### -field pfnCheckMultisampleQualityLevels

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels">CheckMultisampleQualityLevels</a> function.


### -field pfnCheckCounterInfo

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo">CheckCounterInfo</a> function.


### -field pfnCheckCounter

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkcounter">CheckCounter</a> function.


### -field pfnDestroyDevice

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydevice">DestroyDevice(D3D10)</a> function.


### -field pfnSetTextFilterSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_settextfiltersize">SetTextFilterSize</a> function.

<b>The following two functions are supported beginning with Windows Vista with Service Pack 1 (SP1) and Windows Server 2008:  </b>


### -field pfnResourceConvert

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy">ResourceCopy</a> function. For more information about whether to implement a separate <b>ResourceConvert</b> function or to point to the multipurpose <i>ResourceCopy</i>, see the Remarks section of <i>ResourceCopy</i>.  


### -field pfnResourceConvertRegion

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion">ResourceCopyRegion</a> function. For more information about whether to implement a separate <b>ResourceConvertRegion</b> function or to point to the multipurpose <i>ResourceCopyRegion</i>, see the Remarks section of <i>ResourceCopyRegion</i>.

<b>The following functions are supported beginning with Windows 7:  </b>


### -field pfnResetPrimitiveID

 


### -field pfnSetVertexPipelineOutput

 


### -field pfnDrawIndexedInstancedIndirect

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_drawindexedinstancedindirect">DrawIndexedInstancedIndirect</a> function.


### -field pfnDrawInstancedIndirect

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_drawinstancedindirect">DrawInstancedIndirect</a> function.


### -field pfnCommandListExecute

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_commandlistexecute">CommandListExecute</a> function. The driver is only required to implement <i>CommandListExecute</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnHsSetShaderResources

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">HsSetShaderResources</a> function.


### -field pfnHsSetShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">HsSetShader</a> function.


### -field pfnHsSetSamplers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">HsSetSamplers</a> function.


### -field pfnHsSetConstantBuffers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">HsSetConstantBuffers</a> function.


### -field pfnDsSetShaderResources

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">DsSetShaderResources</a> function.


### -field pfnDsSetShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">DsSetShader</a> function.


### -field pfnDsSetSamplers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">DsSetSamplers</a> function.


### -field pfnDsSetConstantBuffers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">DsSetConstantBuffers</a> function.


### -field pfnCreateHullShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createhullshader">CreateHullShader</a> function.


### -field pfnCreateDomainShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createdomainshader">CreateDomainShader</a> function.


### -field pfnCheckDeferredContextHandleSizes

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes">CheckDeferredContextHandleSizes</a> function. The driver is only required to implement <i>CheckDeferredContextHandleSizes</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcDeferredContextHandleSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcdeferredcontexthandlesize">CalcDeferredContextHandleSize</a> function. The driver is only required to implement <i>CalcDeferredContextHandleSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateDeferredContextSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatedeferredcontextsize">CalcPrivateDeferredContextSize</a> function. The driver is only required to implement <i>CalcPrivateDeferredContextSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCreateDeferredContext

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createdeferredcontext">CreateDeferredContext</a> function. The driver is only required to implement <i>CreateDeferredContext</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnAbandonCommandList

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist">AbandonCommandList</a> function. The driver is only required to implement <i>AbandonCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateCommandListSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize">CalcPrivateCommandListSize</a> function. The driver is only required to implement <i>CalcPrivateCommandListSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCreateCommandList

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createcommandlist">CreateCommandList</a> function. The driver is only required to implement <i>CreateCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnDestroyCommandList

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_destroycommandlist">DestroyCommandList</a> function. The driver is only required to implement <i>DestroyCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateTessellationShaderSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize">CalcPrivateTessellationShaderSize</a> function. 


### -field pfnPsSetShaderWithIfaces

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">PsSetShaderWithIfaces</a> function. 


### -field pfnVsSetShaderWithIfaces

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">VsSetShaderWithIfaces</a> function. 


### -field pfnGsSetShaderWithIfaces

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">GsSetShaderWithIfaces</a> function. 


### -field pfnHsSetShaderWithIfaces

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">HsSetShaderWithIfaces</a> function. 


### -field pfnDsSetShaderWithIfaces

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">DsSetShaderWithIfaces</a> function. 


### -field pfnCsSetShaderWithIfaces

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces">CsSetShaderWithIfaces</a> function. 


### -field pfnCreateComputeShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createcomputeshader">CreateComputeShader</a> function. 


### -field pfnCsSetShader

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshader">CsSetShader</a> function. 


### -field pfnCsSetShaderResources

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setshaderresources">CsSetShaderResources</a> function. 


### -field pfnCsSetSamplers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setsamplers">CsSetSamplers</a> function. 


### -field pfnCsSetConstantBuffers

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers">CsSetConstantBuffers</a> function. 


### -field pfnCalcPrivateUnorderedAccessViewSize

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize">CalcPrivateUnorderedAccessViewSize</a> function. 


### -field pfnCreateUnorderedAccessView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a> function. 


### -field pfnDestroyUnorderedAccessView

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview">DestroyUnorderedAccessView</a> function. 


### -field pfnClearUnorderedAccessViewUint

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewuint">ClearUnorderedAccessViewUINT</a> function. 


### -field pfnClearUnorderedAccessViewFloat

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewfloat">ClearUnorderedAccessViewFLOAT</a> function. 


### -field pfnCsSetUnorderedAccessViews

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setunorderedaccessviews">CsSetUnorderedAccessViews</a> function. 


### -field pfnDispatch

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_dispatch">Dispatch</a> function. 


### -field pfnDispatchIndirect

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_dispatchindirect">DispatchIndirect</a> function. 


### -field pfnSetResourceMinLOD

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_setresourceminlod">SetResourceMinLOD</a> function. 


### -field pfnCopyStructureCount

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_copystructurecount">CopyStructureCount</a> function. 


### -field pfnRecycleCommandList

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_recyclecommandlist">RecycleCommandList</a> function. 


### -field pfnRecycleCreateCommandList

A pointer to the driver's   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_recyclecreatecommandlist">RecycleCreateCommandList</a> function. 


### -field pfnRecycleCreateDeferredContext

A pointer to the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_recyclecreatedeferredcontext">RecycleCreateDeferredContext</a> function. 


### -field pfnRecycleDestroyCommandList

A pointer to the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_destroycommandlist">RecycleDestroyCommandList</a> function. 


## -remarks



The order of user-mode display driver functions (that is, the order of the members of the D3D11DDI_DEVICEFUNCS structure) is in decreasing order of priority (in regard to performance).

The user-mode display driver can use different names for these functions because the address of the function table (this structure) is shared between the Direct3D 11 runtime and the driver through the call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function.

The <b>pfnResetPrimitiveID</b> and  <b>pfnSetVertexPipelineOutput</b> members (not shown here) and their data types are reserved for system use and should not be used in your driver.

<h3><a id="Deferred_contexts"></a><a id="deferred_contexts"></a><a id="DEFERRED_CONTEXTS"></a>Deferred contexts</h3>
For a list of the functions that are not leveraged for deferred contexts, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/excluding-ddi-functions-for-deferred-contexts">Excluding DDI Functions for Deferred Contexts</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_devicefuncs">D3D11_1DDI_DEVICEFUNCS</a>
 

 

