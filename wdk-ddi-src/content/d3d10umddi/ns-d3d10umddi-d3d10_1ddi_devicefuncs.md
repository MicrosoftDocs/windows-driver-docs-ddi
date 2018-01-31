---
UID: NS:d3d10umddi.D3D10_1DDI_DEVICEFUNCS
title: D3D10_1DDI_DEVICEFUNCS
author: windows-driver-content
description: The D3D10_1DDI_DEVICEFUNCS structure contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 10.1 runtime can implement to render graphics primitives and process state changes.
old-location: display\d3d10_1ddi_devicefuncs.htm
old-project: display
ms.assetid: 6de52d56-deca-4623-81a7-a043b8a85dc5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10_1DDI_DEVICEFUNCS, UMDisplayDriver_Dx10param_Structs_5790b9b0-0f52-4018-bdf7-edd33f423364.xml, d3d10umddi/D3D10_1DDI_DEVICEFUNCS, display.d3d10_1ddi_devicefuncs, D3D10_1DDI_DEVICEFUNCS structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_1DDI_DEVICEFUNCS is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_1DDI_DEVICEFUNCS
product: Windows
targetos: Windows
req.typenames: D3D10_1DDI_DEVICEFUNCS
---

# D3D10_1DDI_DEVICEFUNCS structure


## -description


The D3D10_1DDI_DEVICEFUNCS structure contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 10.1 runtime can implement to render graphics primitives and process state changes.


## -syntax


````
typedef struct D3D10_1DDI_DEVICEFUNCS {
  PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP               pfnDefaultConstantBufferUpdateSubresourceUP;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnVsSetConstantBuffers;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnPsSetShaderResources;
  PFND3D10DDI_SETSHADER                                 pfnPsSetShader;
  PFND3D10DDI_SETSAMPLERS                               pfnPsSetSamplers;
  PFND3D10DDI_SETSHADER                                 pfnVsSetShader;
  PFND3D10DDI_DRAWINDEXED                               pfnDrawIndexed;
  PFND3D10DDI_DRAW                                      pfnDraw;
  PFND3D10DDI_RESOURCEMAP                               pfnDynamicIABufferMapNoOverwrite;
  PFND3D10DDI_RESOURCEUNMAP                             pfnDynamicIABufferUnmap;
  PFND3D10DDI_RESOURCEMAP                               pfnDynamicConstantBufferMapDiscard;
  PFND3D10DDI_RESOURCEMAP                               pfnDynamicIABufferMapDiscard;
  PFND3D10DDI_RESOURCEUNMAP                             pfnDynamicConstantBufferUnmap;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnPsSetConstantBuffers;
  PFND3D10DDI_SETINPUTLAYOUT                            pfnIaSetInputLayout;
  PFND3D10DDI_IA_SETVERTEXBUFFERS                       pfnIaSetVertexBuffers;
  PFND3D10DDI_IA_SETINDEXBUFFER                         pfnIaSetIndexBuffer;
  PFND3D10DDI_DRAWINDEXEDINSTANCED                      pfnDrawIndexedInstanced;
  PFND3D10DDI_DRAWINSTANCED                             pfnDrawInstanced;
  PFND3D10DDI_RESOURCEMAP                               pfnDynamicResourceMapDiscard;
  PFND3D10DDI_RESOURCEUNMAP                             pfnDynamicResourceUnmap;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnGsSetConstantBuffers;
  PFND3D10DDI_SETSHADER                                 pfnGsSetShader;
  PFND3D10DDI_IA_SETTOPOLOGY                            pfnIaSetTopology;
  PFND3D10DDI_RESOURCEMAP                               pfnStagingResourceMap;
  PFND3D10DDI_RESOURCEUNMAP                             pfnStagingResourceUnmap;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnVsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                               pfnVsSetSamplers;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnGsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                               pfnGsSetSamplers;
  PFND3D10DDI_SETRENDERTARGETS                          pfnSetRenderTargets;
  PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD    pfnShaderResourceViewReadAfterWriteHazard;
  PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD              pfnResourceReadAfterWriteHazard;
  PFND3D10DDI_SETBLENDSTATE                             pfnSetBlendState;
  PFND3D10DDI_SETDEPTHSTENCILSTATE                      pfnSetDepthStencilState;
  PFND3D10DDI_SETRASTERIZERSTATE                        pfnSetRasterizerState;
  PFND3D10DDI_QUERYEND                                  pfnQueryEnd;
  PFND3D10DDI_QUERYBEGIN                                pfnQueryBegin;
  PFND3D10DDI_RESOURCECOPYREGION                        pfnResourceCopyRegion;
  PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP               pfnResourceUpdateSubresourceUP;
  PFND3D10DDI_SO_SETTARGETS                             pfnSoSetTargets;
  PFND3D10DDI_DRAWAUTO                                  pfnDrawAuto;
  PFND3D10DDI_SETVIEWPORTS                              pfnSetViewports;
  PFND3D10DDI_SETSCISSORRECTS                           pfnSetScissorRects;
  PFND3D10DDI_CLEARRENDERTARGETVIEW                     pfnClearRenderTargetView;
  PFND3D10DDI_CLEARDEPTHSTENCILVIEW                     pfnClearDepthStencilView;
  PFND3D10DDI_SETPREDICATION                            pfnSetPredication;
  PFND3D10DDI_QUERYGETDATA                              pfnQueryGetData;
  PFND3D10DDI_FLUSH                                     pfnFlush;
  PFND3D10DDI_GENMIPS                                   pfnGenMips;
  PFND3D10DDI_RESOURCECOPY                              pfnResourceCopy;
  PFND3D10DDI_RESOURCERESOLVESUBRESOURCE                pfnResourceResolveSubresource;
  PFND3D10DDI_RESOURCEMAP                               pfnResourceMap;
  PFND3D10DDI_RESOURCEUNMAP                             pfnResourceUnmap;
  PFND3D10DDI_RESOURCEISSTAGINGBUSY                     pfnResourceIsStagingBusy;
  PFND3D10_1DDI_RELOCATEDEVICEFUNCS                     pfnRelocateDeviceFuncs;
  PFND3D10DDI_CALCPRIVATERESOURCESIZE                   pfnCalcPrivateResourceSize;
  PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE             pfnCalcPrivateOpenedResourceSize;
  PFND3D10DDI_CREATERESOURCE                            pfnCreateResource;
  PFND3D10DDI_OPENRESOURCE                              pfnOpenResource;
  PFND3D10DDI_DESTROYRESOURCE                           pfnDestroyResource;
  PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE       pfnCalcPrivateShaderResourceViewSize;
  PFND3D10_1DDI_CREATESHADERRESOURCEVIEW                pfnCreateShaderResourceView;
  PFND3D10DDI_DESTROYSHADERRESOURCEVIEW                 pfnDestroyShaderResourceView;
  PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE           pfnCalcPrivateRenderTargetViewSize;
  PFND3D10DDI_CREATERENDERTARGETVIEW                    pfnCreateRenderTargetView;
  PFND3D10DDI_DESTROYRENDERTARGETVIEW                   pfnDestroyRenderTargetView;
  PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE           pfnCalcPrivateDepthStencilViewSize;
  PFND3D10DDI_CREATEDEPTHSTENCILVIEW                    pfnCreateDepthStencilView;
  PFND3D10DDI_DESTROYDEPTHSTENCILVIEW                   pfnDestroyDepthStencilView;
  PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE              pfnCalcPrivateElementLayoutSize;
  PFND3D10DDI_CREATEELEMENTLAYOUT                       pfnCreateElementLayout;
  PFND3D10DDI_DESTROYELEMENTLAYOUT                      pfnDestroyElementLayout;
  PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE               pfnCalcPrivateBlendStateSize;
  PFND3D10_1DDI_CREATEBLENDSTATE                        pfnCreateBlendState;
  PFND3D10DDI_DESTROYBLENDSTATE                         pfnDestroyBlendState;
  PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE          pfnCalcPrivateDepthStencilStateSize;
  PFND3D10DDI_CREATEDEPTHSTENCILSTATE                   pfnCreateDepthStencilState;
  PFND3D10DDI_DESTROYDEPTHSTENCILSTATE                  pfnDestroyDepthStencilState;
  PFND3D10DDI_CALCPRIVATERASTERIZERSTATESIZE            pfnCalcPrivateRasterizerStateSize;
  PFND3D10DDI_CREATERASTERIZERSTATE                     pfnCreateRasterizerState;
  PFND3D10DDI_DESTROYRASTERIZERSTATE                    pfnDestroyRasterizerState;
  PFND3D10DDI_CALCPRIVATESHADERSIZE                     pfnCalcPrivateShaderSize;
  PFND3D10DDI_CREATEVERTEXSHADER                        pfnCreateVertexShader;
  PFND3D10DDI_CREATEGEOMETRYSHADER                      pfnCreateGeometryShader;
  PFND3D10DDI_CREATEPIXELSHADER                         pfnCreatePixelShader;
  PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT pfnCalcPrivateGeometryShaderWithStreamOutput;
  PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT      pfnCreateGeometryShaderWithStreamOutput;
  PFND3D10DDI_DESTROYSHADER                             pfnDestroyShader;
  PFND3D10DDI_CALCPRIVATESAMPLERSIZE                    pfnCalcPrivateSamplerSize;
  PFND3D10DDI_CREATESAMPLER                             pfnCreateSampler;
  PFND3D10DDI_DESTROYSAMPLER                            pfnDestroySampler;
  PFND3D10DDI_CALCPRIVATEQUERYSIZE                      pfnCalcPrivateQuerySize;
  PFND3D10DDI_CREATEQUERY                               pfnCreateQuery;
  PFND3D10DDI_DESTROYQUERY                              pfnDestroyQuery;
  PFND3D10DDI_CHECKFORMATSUPPORT                        pfnCheckFormatSupport;
  PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS             pfnCheckMultisampleQualityLevels;
  PFND3D10DDI_CHECKCOUNTERINFO                          pfnCheckCounterInfo;
  PFND3D10DDI_CHECKCOUNTER                              pfnCheckCounter;
  PFND3D10DDI_DESTROYDEVICE                             pfnDestroyDevice;
  PFND3D10DDI_SETTEXTFILTERSIZE                         pfnSetTextFilterSize;
  PFND3D10DDI_RESOURCECOPY                              pfnResourceConvert;
  PFND3D10DDI_RESOURCECOPYREGION                        pfnResourceConvertRegion;
} D3D10_1DDI_DEVICEFUNCS;
````


## -struct-fields




#### - pfnDefaultConstantBufferUpdateSubresourceUP

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">DefaultConstantBufferUpdateSubresourceUP</a> function.


#### - pfnVsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">VsSetConstantBuffers</a> function.


#### - pfnPsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">PsSetShaderResources</a> function.


#### - pfnPsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">PsSetShader</a> function. 


#### - pfnPsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">PsSetSamplers</a> function.


#### - pfnVsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">VsSetShader</a> function.


#### - pfnDrawIndexed

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawindexed.md">DrawIndexed</a> function.


#### - pfnDraw

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_draw.md">Draw</a> function.


#### - pfnDynamicIABufferMapNoOverwrite

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicIABufferMapNoOverwrite</b> function or to point to the multipurpose <b>ResourceMap</b>, see the Remarks section of <b>ResourceMap</b>. 


#### - pfnDynamicIABufferUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicIABufferUnmap</b> function or to point to the multipurpose <b>ResourceUnmap</b>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>. 


#### - pfnDynamicConstantBufferMapDiscard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicConstantBufferMapDiscard</b> function or to point to the multipurpose <b>ResourceMap</b>, see the Remarks section of <b>ResourceMap</b>. 


#### - pfnDynamicIABufferMapDiscard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicIABufferMapDiscard</b> function or to point to the multipurpose <b>ResourceMap</b>, see the Remarks section of <b>ResourceMap</b>. 


#### - pfnDynamicConstantBufferUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicConstantBufferUnmap</b> function or to point to the multipurpose <b>ResourceUnmap</b>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>. 


#### - pfnPsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">PsSetConstantBuffers</a> function.


#### - pfnIaSetInputLayout

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setinputlayout.md">IaSetInputLayout</a> function.


#### - pfnIaSetVertexBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setvertexbuffers.md">IaSetVertexBuffers</a> function.


#### - pfnIaSetIndexBuffer

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer.md">IaSetIndexBuffer</a> function.


#### - pfnDrawIndexedInstanced

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced.md">DrawIndexedInstanced</a> function.


#### - pfnDrawInstanced

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawinstanced.md">DrawInstanced</a> function.


#### - pfnDynamicResourceMapDiscard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicResourceMapDiscard</b> function or to point to the multipurpose <b>ResourceMap</b>, see the Remarks section of <b>ResourceMap</b>. 


#### - pfnDynamicResourceUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicResourceUnmap</b> function or to point to the multipurpose <b>ResourceUnmap</b>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>. 


#### - pfnGsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">GsSetConstantBuffers</a> function.


#### - pfnGsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">GsSetShader</a> function.


#### - pfnIaSetTopology

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_settopology.md">IaSetTopology</a> function.


#### - pfnStagingResourceMap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>StagingResourceMap</b> function or to point to the multipurpose <b>ResourceMap</b>, see the Remarks section of <b>ResourceMap</b>. 


#### - pfnStagingResourceUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <b>StagingResourceUnmap</b> function or to point to the multipurpose <b>ResourceUnmap</b>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>. 


#### - pfnVsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">VsSetShaderResources</a> function.


#### - pfnVsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">VsSetSamplers</a> function.


#### - pfnGsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">GsSetShaderResources</a> function.


#### - pfnGsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">GsSetSamplers</a> function.


#### - pfnSetRenderTargets

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setrendertargets.md">SetRenderTargets</a> function.


#### - pfnShaderResourceViewReadAfterWriteHazard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_shaderresourceviewreadafterwritehazard.md">ShaderResourceViewReadAfterWriteHazard</a> function.


#### - pfnResourceReadAfterWriteHazard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcereadafterwritehazard.md">ResourceReadAfterWriteHazard</a> function.


#### - pfnSetBlendState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setblendstate.md">SetBlendState</a> function.


#### - pfnSetDepthStencilState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setdepthstencilstate.md">SetDepthStencilState</a> function.


#### - pfnSetRasterizerState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setrasterizerstate.md">SetRasterizerState</a> function.


#### - pfnQueryEnd

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_queryend.md">QueryEnd</a> function.


#### - pfnQueryBegin

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querybegin.md">QueryBegin</a> function.


#### - pfnResourceCopyRegion

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md">ResourceCopyRegion</a> function.


#### - pfnResourceUpdateSubresourceUP

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a> function.


#### - pfnSoSetTargets

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_so_settargets.md">SoSetTargets</a> function.


#### - pfnDrawAuto

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawauto.md">DrawAuto</a> function.


#### - pfnSetViewports

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setviewports.md">SetViewports</a> function.


#### - pfnSetScissorRects

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setscissorrects.md">SetScissorRects</a> function.


#### - pfnClearRenderTargetView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_clearrendertargetview.md">ClearRenderTargetView</a> function.


#### - pfnClearDepthStencilView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_cleardepthstencilview.md">ClearDepthStencilView</a> function.


#### - pfnSetPredication

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a> function.


#### - pfnQueryGetData

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function.


#### - pfnFlush

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_flush.md">Flush(D3D10)</a> function.


#### - pfnGenMips

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_genmips.md">GenMips</a> function.


#### - pfnResourceCopy

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md">ResourceCopy</a> function.


#### - pfnResourceResolveSubresource

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceresolvesubresource.md">ResourceResolveSubresource</a> function.


#### - pfnResourceMap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function.


#### - pfnResourceUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function.


#### - pfnResourceIsStagingBusy

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy.md">ResourceIsStagingBusy</a> function.


#### - pfnRelocateDeviceFuncs

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_relocatedevicefuncs.md">RelocateDeviceFuncs(D3D10_1)</a> function.


#### - pfnCalcPrivateResourceSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateresourcesize.md">CalcPrivateResourceSize</a> function.


#### - pfnCalcPrivateOpenedResourceSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateopenedresourcesize.md">CalcPrivateOpenedResourceSize</a> function.


#### - pfnCreateResource

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> function.


#### - pfnOpenResource

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openresource.md">OpenResource(D3D10)</a> function.


#### - pfnDestroyResource

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyresource.md">DestroyResource(D3D10)</a> function.


#### - pfnCalcPrivateShaderResourceViewSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize(D3D10_1)</a> function.


#### - pfnCreateShaderResourceView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview.md">CreateShaderResourceView(D3D10_1)</a> function.


#### - pfnDestroyShaderResourceView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview.md">DestroyShaderResourceView</a> function.


#### - pfnCalcPrivateRenderTargetViewSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a> function.


#### - pfnCreateRenderTargetView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a> function.


#### - pfnDestroyRenderTargetView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview.md">DestroyRenderTargetView</a> function.


#### - pfnCalcPrivateDepthStencilViewSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize.md">CalcPrivateDepthStencilViewSize</a> function.


#### - pfnCreateDepthStencilView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview.md">CreateDepthStencilView</a> function.


#### - pfnDestroyDepthStencilView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview.md">DestroyDepthStencilView</a> function.


#### - pfnCalcPrivateElementLayoutSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize.md">CalcPrivateElementLayoutSize</a> function.


#### - pfnCreateElementLayout

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createelementlayout.md">CreateElementLayout</a> function.


#### - pfnDestroyElementLayout

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout.md">DestroyElementLayout</a> function.


#### - pfnCalcPrivateBlendStateSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D10_1)</a> function.


#### - pfnCreateBlendState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_createblendstate.md">CreateBlendState(D3D10_1)</a> function.


#### - pfnDestroyBlendState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyblendstate.md">DestroyBlendState</a> function.


#### - pfnCalcPrivateDepthStencilStateSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize.md">CalcPrivateDepthStencilStateSize</a> function.


#### - pfnCreateDepthStencilState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate.md">CreateDepthStencilState</a> function.


#### - pfnDestroyDepthStencilState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilstate.md">DestroyDepthStencilState</a> function.


#### - pfnCalcPrivateRasterizerStateSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterasterizerstatesize.md">CalcPrivateRasterizerStateSize</a> function.


#### - pfnCreateRasterizerState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrasterizerstate.md">CreateRasterizerState</a> function.


#### - pfnDestroyRasterizerState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate.md">DestroyRasterizerState</a> function.


#### - pfnCalcPrivateShaderSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize.md">CalcPrivateShaderSize</a> function.


#### - pfnCreateVertexShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createvertexshader.md">CreateVertexShader(D3D10)</a> function.


#### - pfnCreateGeometryShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_creategeometryshader.md">CreateGeometryShader</a> function.


#### - pfnCreatePixelShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createpixelshader.md">CreatePixelShader(D3D10)</a> function.


#### - pfnCalcPrivateGeometryShaderWithStreamOutput

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput</a> function.


#### - pfnCreateGeometryShaderWithStreamOutput

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_creategeometryshaderwithstreamoutput.md">CreateGeometryShaderWithStreamOutput</a> function.


#### - pfnDestroyShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshader.md">DestroyShader</a> function.


#### - pfnCalcPrivateSamplerSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize.md">CalcPrivateSamplerSize</a> function.


#### - pfnCreateSampler

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createsampler.md">CreateSampler</a> function.


#### - pfnDestroySampler

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroysampler.md">DestroySampler</a> function.


#### - pfnCalcPrivateQuerySize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatequerysize.md">CalcPrivateQuerySize</a> function.


#### - pfnCreateQuery

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function.


#### - pfnDestroyQuery

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyquery.md">DestroyQuery(D3D10)</a> function.


#### - pfnCheckFormatSupport

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkformatsupport.md">CheckFormatSupport</a> function.


#### - pfnCheckMultisampleQualityLevels

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels.md">CheckMultisampleQualityLevels</a> function.


#### - pfnCheckCounterInfo

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo.md">CheckCounterInfo</a> function.


#### - pfnCheckCounter

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounter.md">CheckCounter</a> function.


#### - pfnDestroyDevice

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice(D3D10)</a> function.


#### - pfnSetTextFilterSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_settextfiltersize.md">SetTextFilterSize</a> function.


#### - pfnResourceConvert

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md">ResourceCopy</a> function. For more information about whether to implement a separate <b>ResourceConvert</b> function or to point to the multipurpose <b>ResourceCopy</b>, see the Remarks section of <b>ResourceCopy</b>.  


#### - pfnResourceConvertRegion

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md">ResourceCopyRegion</a> function. For more information about whether to implement a separate <b>ResourceConvertRegion</b> function or to point to the multipurpose <b>ResourceCopyRegion</b>, see the Remarks section of <b>ResourceCopyRegion</b>.  


### -field pfnResetPrimitiveID

 


### -field pfnSetVertexPipelineOutput

 



## -remarks


The order of user-mode display driver functions (that is, the order of the members of the D3D10_1DDI_DEVICEFUNCS structure) is in decreasing order of priority (in regard to performance).

The user-mode display driver can use different names for these functions because the address of the function table (this structure) is shared between the Direct3D 10.1 runtime and the driver through the call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function.

The <b>pfnResetPrimitiveID</b> and  <b>pfnSetVertexPipelineOutput</b> members (not shown here) and their data types are reserved for system use and should not be used in your driver.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_1DDI_DEVICEFUNCS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

