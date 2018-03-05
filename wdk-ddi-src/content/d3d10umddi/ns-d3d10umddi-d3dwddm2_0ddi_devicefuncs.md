---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_DEVICEFUNCS
title: D3DWDDM2_0DDI_DEVICEFUNCS
author: windows-driver-content
description: This structure contains the user mode device function table for Windows Display Driver Model (WDDM) 2.0.
old-location: display\d3dwddm2_0ddi_devicefuncs.htm
old-project: display
ms.assetid: 9A41512A-91C4-4053-9C60-5B485E93D14B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DWDDM2_0DDI_DEVICEFUNCS, D3DWDDM2_0DDI_DEVICEFUNCS structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_DEVICEFUNCS, display.d3dwddm2_0ddi_devicefuncs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_DEVICEFUNCS
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_DEVICEFUNCS, D3DWDDM2_0DDI_DEVICEFUNCS, D3DWDDM2_0DDI_DEVICEFUNCS
---

# D3DWDDM2_0DDI_DEVICEFUNCS structure


## -description


This structure contains the user mode device function table for Windows Display Driver Model (WDDM) 2.0.


## -syntax


````
typedef struct D3DWDDM2_0DDI_DEVICEFUNCS {
  PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP               pfnDefaultConstantBufferUpdateSubresourceUP;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnVsSetConstantBuffers;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnPsSetShaderResources;
  PFND3D10DDI_SETSHADER                                   pfnPsSetShader;
  PFND3D10DDI_SETSAMPLERS                                 pfnPsSetSamplers;
  PFND3D10DDI_SETSHADER                                   pfnVsSetShader;
  PFND3D10DDI_DRAWINDEXED                                 pfnDrawIndexed;
  PFND3D10DDI_DRAW                                        pfnDraw;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnPsSetConstantBuffers;
  PFND3D10DDI_SETINPUTLAYOUT                              pfnIaSetInputLayout;
  PFND3D10DDI_IA_SETVERTEXBUFFERS                         pfnIaSetVertexBuffers;
  PFND3D10DDI_IA_SETINDEXBUFFER                           pfnIaSetIndexBuffer;
  PFND3D10DDI_DRAWINDEXEDINSTANCED                        pfnDrawIndexedInstanced;
  PFND3D10DDI_DRAWINSTANCED                               pfnDrawInstanced;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnGsSetConstantBuffers;
  PFND3D10DDI_SETSHADER                                   pfnGsSetShader;
  PFND3D10DDI_IA_SETTOPOLOGY                              pfnIaSetTopology;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnVsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                                 pfnVsSetSamplers;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnGsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                                 pfnGsSetSamplers;
  PFND3D11DDI_SETRENDERTARGETS                            pfnSetRenderTargets;
  PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD      pfnShaderResourceViewReadAfterWriteHazard;
  PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD                pfnResourceReadAfterWriteHazard;
  PFND3D10DDI_SETBLENDSTATE                               pfnSetBlendState;
  PFND3D10DDI_SETDEPTHSTENCILSTATE                        pfnSetDepthStencilState;
  PFND3D10DDI_SETRASTERIZERSTATE                          pfnSetRasterizerState;
  PFND3D10DDI_QUERYEND                                    pfnQueryEnd;
  PFND3D10DDI_QUERYBEGIN                                  pfnQueryBegin;
  PFND3D11_1DDI_RESOURCECOPYREGION                        pfnResourceCopyRegion;
  PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP               pfnResourceUpdateSubresourceUP;
  PFND3D10DDI_SO_SETTARGETS                               pfnSoSetTargets;
  PFND3D10DDI_DRAWAUTO                                    pfnDrawAuto;
  PFND3D10DDI_SETVIEWPORTS                                pfnSetViewports;
  PFND3D10DDI_SETSCISSORRECTS                             pfnSetScissorRects;
  PFND3D10DDI_CLEARRENDERTARGETVIEW                       pfnClearRenderTargetView;
  PFND3D10DDI_CLEARDEPTHSTENCILVIEW                       pfnClearDepthStencilView;
  PFND3D10DDI_SETPREDICATION                              pfnSetPredication;
  PFND3D10DDI_QUERYGETDATA                                pfnQueryGetData;
  PFND3D11_1DDI_FLUSH                                     pfnFlush;
  PFND3D10DDI_GENMIPS                                     pfnGenMips;
  PFND3D10DDI_RESOURCECOPY                                pfnResourceCopy;
  PFND3D10DDI_RESOURCERESOLVESUBRESOURCE                  pfnResourceResolveSubresource;
  PFND3D10DDI_RESOURCEMAP                                 pfnResourceMap;
  PFND3D10DDI_RESOURCEUNMAP                               pfnResourceUnmap;
  PFND3D10DDI_RESOURCEISSTAGINGBUSY                       pfnResourceIsStagingBusy;
  PFND3DWDDM2_0DDI_RELOCATEDEVICEFUNCS                    pfnRelocateDeviceFuncs;
  PFND3D11DDI_CALCPRIVATERESOURCESIZE                     pfnCalcPrivateResourceSize;
  PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE               pfnCalcPrivateOpenedResourceSize;
  PFND3D11DDI_CREATERESOURCE                              pfnCreateResource;
  PFND3D10DDI_OPENRESOURCE                                pfnOpenResource;
  PFND3D10DDI_DESTROYRESOURCE                             pfnDestroyResource;
  PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE           pfnCalcPrivateShaderResourceViewSize;
  PFND3D11DDI_CREATESHADERRESOURCEVIEW                    pfnCreateShaderResourceView;
  PFND3D10DDI_DESTROYSHADERRESOURCEVIEW                   pfnDestroyShaderResourceView;
  PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE             pfnCalcPrivateRenderTargetViewSize;
  PFND3D10DDI_CREATERENDERTARGETVIEW                      pfnCreateRenderTargetView;
  PFND3D10DDI_DESTROYRENDERTARGETVIEW                     pfnDestroyRenderTargetView;
  PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE             pfnCalcPrivateDepthStencilViewSize;
  PFND3D11DDI_CREATEDEPTHSTENCILVIEW                      pfnCreateDepthStencilView;
  PFND3D10DDI_DESTROYDEPTHSTENCILVIEW                     pfnDestroyDepthStencilView;
  PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE                pfnCalcPrivateElementLayoutSize;
  PFND3D10DDI_CREATEELEMENTLAYOUT                         pfnCreateElementLayout;
  PFND3D10DDI_DESTROYELEMENTLAYOUT                        pfnDestroyElementLayout;
  PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE                 pfnCalcPrivateBlendStateSize;
  PFND3D11_1DDI_CREATEBLENDSTATE                          pfnCreateBlendState;
  PFND3D10DDI_DESTROYBLENDSTATE                           pfnDestroyBlendState;
  PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE            pfnCalcPrivateDepthStencilStateSize;
  PFND3D10DDI_CREATEDEPTHSTENCILSTATE                     pfnCreateDepthStencilState;
  PFND3D10DDI_DESTROYDEPTHSTENCILSTATE                    pfnDestroyDepthStencilState;
  PFND3DWDDM2_0DDI_CALCPRIVATERASTERIZERSTATESIZE         pfnCalcPrivateRasterizerStateSize;
  PFND3DWDDM2_0DDI_CREATERASTERIZERSTATE                  pfnCreateRasterizerState;
  PFND3D10DDI_DESTROYRASTERIZERSTATE                      pfnDestroyRasterizerState;
  PFND3D11_1DDI_CALCPRIVATESHADERSIZE                     pfnCalcPrivateShaderSize;
  PFND3D11_1DDI_CREATEVERTEXSHADER                        pfnCreateVertexShader;
  PFND3D11_1DDI_CREATEGEOMETRYSHADER                      pfnCreateGeometryShader;
  PFND3D11_1DDI_CREATEPIXELSHADER                         pfnCreatePixelShader;
  PFND3D11_1DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT pfnCalcPrivateGeometryShaderWithStreamOutput;
  PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT      pfnCreateGeometryShaderWithStreamOutput;
  PFND3D10DDI_DESTROYSHADER                               pfnDestroyShader;
  PFND3D10DDI_CALCPRIVATESAMPLERSIZE                      pfnCalcPrivateSamplerSize;
  PFND3D10DDI_CREATESAMPLER                               pfnCreateSampler;
  PFND3D10DDI_DESTROYSAMPLER                              pfnDestroySampler;
  PFND3D10DDI_CALCPRIVATEQUERYSIZE                        pfnCalcPrivateQuerySize;
  PFND3D10DDI_CREATEQUERY                                 pfnCreateQuery;
  PFND3D10DDI_DESTROYQUERY                                pfnDestroyQuery;
  PFND3D10DDI_CHECKFORMATSUPPORT                          pfnCheckFormatSupport;
  PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS          pfnCheckMultisampleQualityLevels;
  PFND3D10DDI_CHECKCOUNTERINFO                            pfnCheckCounterInfo;
  PFND3D10DDI_CHECKCOUNTER                                pfnCheckCounter;
  PFND3D10DDI_DESTROYDEVICE                               pfnDestroyDevice;
  PFND3D10DDI_SETTEXTFILTERSIZE                           pfnSetTextFilterSize;
  PFND3D11DDI_DRAWINDEXEDINSTANCEDINDIRECT                pfnDrawIndexedInstancedIndirect;
  PFND3D11DDI_DRAWINSTANCEDINDIRECT                       pfnDrawInstancedIndirect;
  PFND3D11DDI_COMMANDLISTEXECUTE                          pfnCommandListExecute;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnHsSetShaderResources;
  PFND3D10DDI_SETSHADER                                   pfnHsSetShader;
  PFND3D10DDI_SETSAMPLERS                                 pfnHsSetSamplers;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnHsSetConstantBuffers;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnDsSetShaderResources;
  PFND3D10DDI_SETSHADER                                   pfnDsSetShader;
  PFND3D10DDI_SETSAMPLERS                                 pfnDsSetSamplers;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnDsSetConstantBuffers;
  PFND3D11_1DDI_CREATEHULLSHADER                          pfnCreateHullShader;
  PFND3D11_1DDI_CREATEDOMAINSHADER                        pfnCreateDomainShader;
  PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES             pfnCheckDeferredContextHandleSizes;
  PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE               pfnCalcDeferredContextHandleSize;
  PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE              pfnCalcPrivateDeferredContextSize;
  PFND3D11DDI_CREATEDEFERREDCONTEXT                       pfnCreateDeferredContext;
  PFND3D11DDI_ABANDONCOMMANDLIST                          pfnAbandonCommandList;
  PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE                  pfnCalcPrivateCommandListSize;
  PFND3D11DDI_CREATECOMMANDLIST                           pfnCreateCommandList;
  PFND3D11DDI_DESTROYCOMMANDLIST                          pfnDestroyCommandList;
  PFND3D11_1DDI_CALCPRIVATETESSELLATIONSHADERSIZE         pfnCalcPrivateTessellationShaderSize;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnPsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnVsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnGsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnHsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnDsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnCsSetShaderWithIfaces;
  PFND3D11DDI_CREATECOMPUTESHADER                         pfnCreateComputeShader;
  PFND3D10DDI_SETSHADER                                   pfnCsSetShader;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnCsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                                 pfnCsSetSamplers;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnCsSetConstantBuffers;
  PFND3D11DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE          pfnCalcPrivateUnorderedAccessViewSize;
  PFND3D11DDI_CREATEUNORDEREDACCESSVIEW                   pfnCreateUnorderedAccessView;
  PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW                  pfnDestroyUnorderedAccessView;
  PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT                pfnClearUnorderedAccessViewUint;
  PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT               pfnClearUnorderedAccessViewFloat;
  PFND3D11DDI_SETUNORDEREDACCESSVIEWS                     pfnCsSetUnorderedAccessViews;
  PFND3D11DDI_DISPATCH                                    pfnDispatch;
  PFND3D11DDI_DISPATCHINDIRECT                            pfnDispatchIndirect;
  PFND3D11DDI_SETRESOURCEMINLOD                           pfnSetResourceMinLOD;
  PFND3D11DDI_COPYSTRUCTURECOUNT                          pfnCopyStructureCount;
  PFND3D11DDI_RECYCLECOMMANDLIST                          pfnRecycleCommandList;
  PFND3D11DDI_RECYCLECREATECOMMANDLIST                    pfnRecycleCreateCommandList;
  PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT                pfnRecycleCreateDeferredContext;
  PFND3D11_1DDI_DISCARD                                   pfnDiscard;
  PFND3D11_1DDI_ASSIGNDEBUGBINARY                         pfnAssignDebugBinary;
  PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT                    pfnCheckDirectFlipSupport;
  PFND3D11_1DDI_CLEARVIEW                                 pfnClearView;
  PFND3DWDDM1_3DDI_UPDATETILEMAPPINGS                     pfnUpdateTileMappings;
  PFND3DWDDM1_3DDI_COPYTILEMAPPINGS                       pfnCopyTileMappings;
  PFND3DWDDM1_3DDI_COPYTILES                              pfnCopyTiles;
  PFND3DWDDM1_3DDI_UPDATETILES                            pfnUpdateTiles;
  PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER                   pfnTiledResourceBarrier;
  PFND3DWDDM1_3DDI_GETMIPPACKING                          pfnGetMipPacking;
  PFND3DWDDM1_3DDI_RESIZETILEPOOL                         pfnResizeTilePool;
  PFND3DWDDM1_3DDI_SETMARKER                              pfnSetMarker;
  PFND3DWDDM1_3DDI_SETMARKERMODE                          pfnSetMarkerMode;
  PFND3DWDDM2_0DDI_SETHARDWAREPROTECTION                  pfnSetHardwareProtection;
} D3DWDDM2_0DDI_DEVICEFUNCS;
````


## -struct-fields




### -field pfnDefaultConstantBufferUpdateSubresourceUP

A pointer to the <a href="https://msdn.microsoft.com/80086f1a-75f8-464f-973e-9c1e67725933">DefaultConstantBufferUpdateSubresourceUP</a> function.


### -field pfnVsSetConstantBuffers

A pointer to the <a href="https://msdn.microsoft.com/38a27fa3-905a-4ab7-b018-53ea3c589661">VsSetConstantBuffers</a> function.


### -field pfnPsSetShaderResources

A pointer to the <a href="https://msdn.microsoft.com/e30aabdd-52b7-40c0-bb92-50cbabdc5e1f">PsSetShaderResources</a> function.


### -field pfnPsSetShader

A pointer to the <a href="https://msdn.microsoft.com/bc6213cd-8e0c-4f10-8942-c42818b512dc">PsSetShader</a> function.


### -field pfnPsSetSamplers

A pointer to the <a href="https://msdn.microsoft.com/3c4b36a9-842c-45dd-a261-74b5ceed5b12">PsSetSamplers</a> function.


### -field pfnVsSetShader

A pointer to the <a href="https://msdn.microsoft.com/6bcafd44-3503-44f7-8676-c27eda585f9d">VsSetShader</a> function.


### -field pfnDrawIndexed

A pointer to the <a href="https://msdn.microsoft.com/d1097bb6-35ac-4069-ae05-b74c75a98e21">DrawIndexed</a> function.


### -field pfnDraw

A pointer to the <a href="https://msdn.microsoft.com/7a6f1d56-12be-4185-97bf-06f265ee6fe3">Draw</a> function.


### -field pfnDynamicIABufferMapNoOverwrite

 


### -field pfnDynamicIABufferUnmap

 


### -field pfnDynamicConstantBufferMapDiscard

 


### -field pfnDynamicIABufferMapDiscard

 


### -field pfnDynamicConstantBufferUnmap

 


### -field pfnPsSetConstantBuffers

A pointer to the <a href="https://msdn.microsoft.com/d77070d8-daf8-44d3-9032-a7a7d3c2c242">PsSetConstantBuffers</a> function.


### -field pfnIaSetInputLayout

A pointer to the <a href="https://msdn.microsoft.com/905e4e7f-5bc5-487f-8d82-4ebc2db66135">IaSetInputLayout</a> function.


### -field pfnIaSetVertexBuffers

A pointer to the <a href="https://msdn.microsoft.com/3d5a7ea1-08c2-4594-93bc-97b985cd16dc">IaSetVertexBuffers</a> function.


### -field pfnIaSetIndexBuffer

A pointer to the <a href="https://msdn.microsoft.com/042ebb72-b794-4cb8-9d81-bd52a785f1e0">IaSetIndexBuffer</a> function.


### -field pfnDrawIndexedInstanced

A pointer to the <a href="https://msdn.microsoft.com/3dc64562-9dc0-4d43-835d-6fdd509435f8">DrawIndexedInstanced</a> function.


### -field pfnDrawInstanced

A pointer to the <a href="https://msdn.microsoft.com/c539cf8b-e056-476a-9b23-7e360917a7d9">DrawInstanced</a> function.


### -field pfnDynamicResourceMapDiscard

 


### -field pfnDynamicResourceUnmap

 


### -field pfnGsSetConstantBuffers

A pointer to the <a href="https://msdn.microsoft.com/1d13fe21-55bc-46c0-b07e-3c96f671496c">GsSetConstantBuffers</a> function.


### -field pfnGsSetShader

A pointer to the <a href="https://msdn.microsoft.com/9f40371d-4a74-4020-af8a-e3781d1bc632">GsSetShader</a> function.


### -field pfnIaSetTopology

A pointer to the <a href="https://msdn.microsoft.com/c2ee9c8b-7e33-4fc9-9bd3-2b2984e94390">IaSetTopology</a> function.


### -field pfnStagingResourceMap

 


### -field pfnStagingResourceUnmap

 


### -field pfnVsSetShaderResources

A pointer to the <a href="https://msdn.microsoft.com/4d432517-97f0-441f-ac49-0416ac19b319">VsSetShaderResources</a> function.


### -field pfnVsSetSamplers

A pointer to the <a href="https://msdn.microsoft.com/3f2c08e2-8372-45a7-9d65-936889f21e27">VsSetSamplers</a> function.


### -field pfnGsSetShaderResources

A pointer to the <a href="https://msdn.microsoft.com/b5cd87bb-7a08-444c-9120-d7ab79e512c5">GsSetShaderResources</a> function.


### -field pfnGsSetSamplers

A pointer to the <a href="https://msdn.microsoft.com/a70b7b29-99d2-4e7e-aeb3-bf324d71ebaf">GsSetSamplers</a> function.


### -field pfnSetRenderTargets

A pointer to the <a href="https://msdn.microsoft.com/852893e6-1f1c-470a-ab72-f52c1e06e0c0">SetRenderTargets</a> function.


### -field pfnShaderResourceViewReadAfterWriteHazard

A pointer to the <a href="https://msdn.microsoft.com/bb391154-a9ff-4032-b86e-81fa4ea2e37c">ShaderResourceViewReadAfterWriteHazard</a> function.


### -field pfnResourceReadAfterWriteHazard

A pointer to the <a href="https://msdn.microsoft.com/4d7dd4f5-9792-48cb-bf69-3903ac9dda75">ResourceReadAfterWriteHazard</a> function.


### -field pfnSetBlendState

A pointer to the <a href="https://msdn.microsoft.com/8794413f-f4d5-4382-8886-2f0659d8a781">SetBlendState</a> function.


### -field pfnSetDepthStencilState

A pointer to the <a href="https://msdn.microsoft.com/379f8113-b07c-4984-ba37-a06d6c21b9e9">SetDepthStencilState</a> function.


### -field pfnSetRasterizerState

A pointer to the <a href="https://msdn.microsoft.com/8162c9c9-4ebd-45a9-adaf-576f25c3907e">SetRasterizerState</a> function.


### -field pfnQueryEnd

A pointer to the <a href="https://msdn.microsoft.com/5a231d7e-7e47-40ad-99d1-82661dec41d0">QueryEnd</a> function.


### -field pfnQueryBegin

A pointer to the <a href="https://msdn.microsoft.com/2f0a7462-83a6-47df-b5f6-b3706b875349">QueryBegin</a> function.


### -field pfnResourceCopyRegion

A pointer to the <a href="https://msdn.microsoft.com/e782dc8c-e34e-4f96-b6d9-c34d7843ed05">ResourceCopyRegion</a> function.


### -field pfnResourceUpdateSubresourceUP

A pointer to the <a href="https://msdn.microsoft.com/3b6177f4-43a1-4461-abfc-5c463b0ba612">ResourceUpdateSubresourceUP</a> function.


### -field pfnSoSetTargets

A pointer to the <a href="https://msdn.microsoft.com/96f1c439-7323-456e-8c9c-793d8e0973d9">SoSetTargets</a> function.


### -field pfnDrawAuto

A pointer to the <a href="https://msdn.microsoft.com/83d96dc0-dfd4-449e-9e14-18f354d44534">DrawAuto</a> function.


### -field pfnSetViewports

A pointer to the <a href="https://msdn.microsoft.com/f5a55dd3-a8c4-4741-b99e-105021d79603">SetViewports</a> function.


### -field pfnSetScissorRects

A pointer to the <a href="https://msdn.microsoft.com/ef61f50b-a82b-43df-865f-2f9d9ca906d4">SetScissorRects</a> function.


### -field pfnClearRenderTargetView

A pointer to the <a href="https://msdn.microsoft.com/9dc95dd2-01ad-45d7-9e75-049026b25968">ClearRenderTargetView</a> function.


### -field pfnClearDepthStencilView

A pointer to the <a href="https://msdn.microsoft.com/0474c154-1bec-4602-880c-ffdc48c738f0">ClearDepthStencilView</a> function.


### -field pfnSetPredication

A pointer to the <a href="https://msdn.microsoft.com/df671478-859f-4ccd-9ab4-1986f9af10cf">SetPredication</a> function.


### -field pfnQueryGetData

A pointer to the <a href="https://msdn.microsoft.com/78ee9813-e23e-4d46-acc4-f2fa88559b03">QueryGetData</a> function.


### -field pfnFlush

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a> function.


### -field pfnGenMips

A pointer to the <a href="https://msdn.microsoft.com/abd045f2-9c05-4579-8d80-aba31523157d">GenMips</a> function.


### -field pfnResourceCopy

A pointer to the <a href="https://msdn.microsoft.com/9a837f42-0bea-4425-b693-dd7947ac24b1">ResourceCopy</a> function.


### -field pfnResourceResolveSubresource

A pointer to the <a href="https://msdn.microsoft.com/f9f4a6e2-bc01-477f-a919-ec71871f665b">ResourceResolveSubresource</a> function.


### -field pfnResourceMap

A pointer to the <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function.


### -field pfnResourceUnmap

A pointer to the <a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a> function.


### -field pfnResourceIsStagingBusy

A pointer to the <a href="https://msdn.microsoft.com/df8498e2-a3b5-4bc8-b6d2-0d444f1d1485">ResourceIsStagingBusy</a> function.


### -field pfnRelocateDeviceFuncs

A pointer to the <a href="https://msdn.microsoft.com/3932a2a1-7b1d-4921-bd4a-905b44166091">RelocateDeviceFuncs</a> function.


### -field pfnCalcPrivateResourceSize

A pointer to the <a href="https://msdn.microsoft.com/2c4eb002-4788-46ab-92b9-3bb2dcb44ee3">CalcPrivateResourceSize</a> function.


### -field pfnCalcPrivateOpenedResourceSize

A pointer to the <a href="https://msdn.microsoft.com/000688fb-6475-4dab-bb65-91c899a592a7">CalcPrivateOpenedResourceSize</a> function.


### -field pfnCreateResource

A pointer to the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function.


### -field pfnOpenResource

A pointer to the <a href="https://msdn.microsoft.com/e3f5cec2-391b-40f9-8a4b-afe6b8de2954">OpenResource</a> function.


### -field pfnDestroyResource

A pointer to the <a href="https://msdn.microsoft.com/1af85315-4367-49de-9453-eef62c838c97">DestroyResource</a> function.


### -field pfnCalcPrivateShaderResourceViewSize

A pointer to the <a href="https://msdn.microsoft.com/2abf5ca9-974b-40d7-b71c-43c4fb33dd7c">CalcPrivateShaderResourceViewSize</a> function.


### -field pfnCreateShaderResourceView

A pointer to the <a href="https://msdn.microsoft.com/3b1c998d-3fde-4712-ba74-7c8033033182">CreateShaderResourceView</a> function.


### -field pfnDestroyShaderResourceView

A pointer to the <a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a> function.


### -field pfnCalcPrivateRenderTargetViewSize

A pointer to the <a href="https://msdn.microsoft.com/14d85e4a-960c-4438-9360-a4f2677603b8">CalcPrivateRenderTargetViewSize</a> function.


### -field pfnCreateRenderTargetView

A pointer to the <a href="https://msdn.microsoft.com/bf9fc732-5f9a-4fee-8ea0-19b140789463">CreateRenderTargetView</a> function.


### -field pfnDestroyRenderTargetView

A pointer to the <a href="https://msdn.microsoft.com/ec04fed3-8e43-4f76-af82-b36c7029f0cc">DestroyRenderTargetView</a> function.


### -field pfnCalcPrivateDepthStencilViewSize

A pointer to the <a href="https://msdn.microsoft.com/e5dfa018-f9a5-467f-8e84-9697d5f94689">CalcPrivateDepthStencilViewSize</a> function.


### -field pfnCreateDepthStencilView

A pointer to the <a href="https://msdn.microsoft.com/1a1c28f0-8343-4255-8055-d31eb643b7d5">CreateDepthStencilView</a> function.


### -field pfnDestroyDepthStencilView

A pointer to the <a href="https://msdn.microsoft.com/5cd2b7bd-0231-4f00-a54e-960b9bffa98e">DestroyDepthStencilView</a> function.


### -field pfnCalcPrivateElementLayoutSize

A pointer to the <a href="https://msdn.microsoft.com/9fc80cea-8e4a-467a-b232-74333d2ceb5f">CalcPrivateElementLayoutSize</a> function.


### -field pfnCreateElementLayout

A pointer to the <a href="https://msdn.microsoft.com/5af2189a-a064-4c62-be09-733c1d632983">CreateElementLayout</a> function.


### -field pfnDestroyElementLayout

A pointer to the <a href="https://msdn.microsoft.com/8b6a07b5-5358-45d3-af42-84f8a6327535">DestroyElementLayout</a> function.


### -field pfnCalcPrivateBlendStateSize

A pointer to the <a href="https://msdn.microsoft.com/c13862b0-3136-4a95-bb00-6057f2934068">CalcPrivateBlendStateSize</a> function.


### -field pfnCreateBlendState

A pointer to the <a href="https://msdn.microsoft.com/f203a83c-0108-4e20-9972-06857099378c">CreateBlendState</a> function.


### -field pfnDestroyBlendState

A pointer to the <a href="https://msdn.microsoft.com/56fc1ecf-fd4c-4d36-941b-8fa6cca3b6b4">DestroyBlendState</a> function.


### -field pfnCalcPrivateDepthStencilStateSize

A pointer to the <a href="https://msdn.microsoft.com/dcc02e1e-97e0-4ccd-8329-8219cad5d09a">CalcPrivateDepthStencilStateSize</a> function.


### -field pfnCreateDepthStencilState

A pointer to the <a href="https://msdn.microsoft.com/ed2da104-c4e8-43eb-80e0-10273b575020">CreateDepthStencilState</a> function.


### -field pfnDestroyDepthStencilState

A pointer to the <a href="https://msdn.microsoft.com/5fc537f6-2507-4edd-bfa0-c011dd834a22">DestroyDepthStencilState</a> function.


### -field pfnCalcPrivateRasterizerStateSize

A pointer to the <a href="https://msdn.microsoft.com/8b10b2b8-21b0-451c-9a85-353222d9c288">CalcPrivateRasterizerStateSize</a> function.


### -field pfnCreateRasterizerState

A pointer to the <a href="https://msdn.microsoft.com/4507b92e-2437-4f90-b527-e06773ca1e08">CreateRasterizerState</a> function.


### -field pfnDestroyRasterizerState

A pointer to the <a href="https://msdn.microsoft.com/7d730528-dc97-4490-a9fa-3d7916eef2e6">DestroyRasterizerState</a> function.


### -field pfnCalcPrivateShaderSize

A pointer to the <a href="https://msdn.microsoft.com/76cdddb0-b927-4547-ae1d-f5105905633b">CalcPrivateShaderSize</a> function.


### -field pfnCreateVertexShader

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvertexshader.md">CreateVertexShader</a> function.


### -field pfnCreateGeometryShader

A pointer to the <a href="https://msdn.microsoft.com/b3b422e3-f8da-4aad-a230-7c7e26dd72ec">CreateGeometryShader</a> function.


### -field pfnCreatePixelShader

A pointer to the <a href="https://msdn.microsoft.com/b80a1823-6d91-440f-89e4-f7248579cc8f">CreatePixelShader</a> function.


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

A pointer to the <a href="https://msdn.microsoft.com/3e760b93-e859-4175-a24a-6bf3648db6db">CalcPrivateGeometryShaderWithStreamOutput</a> function.


### -field pfnCreateGeometryShaderWithStreamOutput

A pointer to the <a href="https://msdn.microsoft.com/6ad1573d-4377-4795-8511-5d6cae96ee4f">CreateGeometryShaderWithStreamOutput</a> function.


### -field pfnDestroyShader

A pointer to the <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function.


### -field pfnCalcPrivateSamplerSize

A pointer to the <a href="https://msdn.microsoft.com/7231ba65-f6ed-4b00-a61f-21d8fe26398f">CalcPrivateSamplerSize</a> function.


### -field pfnCreateSampler

A pointer to the <a href="https://msdn.microsoft.com/603bb033-390b-4965-b6ea-6acc2c7a8fcf">CreateSampler</a> function.


### -field pfnDestroySampler

A pointer to the <a href="https://msdn.microsoft.com/8e66de90-c336-43b4-b0ad-cb24cea3638c">DestroySampler</a> function.


### -field pfnCalcPrivateQuerySize

A pointer to the <a href="https://msdn.microsoft.com/59a59aa8-085e-4bf8-8a6f-e08f2aecd894">CalcPrivateQuerySize</a> function.


### -field pfnCreateQuery

A pointer to the <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function.


### -field pfnDestroyQuery

A pointer to the <a href="https://msdn.microsoft.com/c4cef278-1771-4903-a5cf-85674463aff8">DestroyQuery</a> function.


### -field pfnCheckFormatSupport

A pointer to the <a href="https://msdn.microsoft.com/463ab1e5-08b1-45a1-b7d8-bdfacb3d4bdb">CheckFormatSupport</a> function.


### -field pfnCheckMultisampleQualityLevels

A pointer to the <a href="https://msdn.microsoft.com/2b6a0ab8-f197-48c3-baf2-305b77b7e8b5">CheckMultisampleQualityLevels</a> function.


### -field pfnCheckCounterInfo

A pointer to the <a href="https://msdn.microsoft.com/5dcea47c-aac7-46e5-afd5-c3390c3c5286">CheckCounterInfo</a> function.


### -field pfnCheckCounter

A pointer to the <a href="https://msdn.microsoft.com/592a5146-a2fe-41d1-854b-df27a97bd513">CheckCounter</a> function.


### -field pfnDestroyDevice

A pointer to the <a href="https://msdn.microsoft.com/a3c158c2-6c0d-4da0-80f4-569971b10673">DestroyDevice</a> function.


### -field pfnSetTextFilterSize

A pointer to the <a href="https://msdn.microsoft.com/663fd3c3-7a8f-446d-b45a-392716116407">SetTextFilterSize</a> function.


### -field pfnResourceConvert

 


### -field pfnResourceConvertRegion

 


### -field pfnResetPrimitiveID

 


### -field pfnSetVertexPipelineOutput

 


### -field pfnDrawIndexedInstancedIndirect

A pointer to the <a href="https://msdn.microsoft.com/3debfb11-4de9-456b-a094-feb2f68e96a5">DrawIndexedInstancedIndirect</a> function.


### -field pfnDrawInstancedIndirect

A pointer to the <a href="https://msdn.microsoft.com/99520dae-3934-496f-80bf-e5b306554415">DrawInstancedIndirect</a> function.


### -field pfnCommandListExecute

A pointer to the <a href="https://msdn.microsoft.com/49f44f29-52f6-40d9-8617-a24aa3d30736">CommandListExecute</a> function.


### -field pfnHsSetShaderResources

A pointer to the <a href="https://msdn.microsoft.com/54449d80-4943-4178-99cb-0ceed498600c">HsSetShaderResources</a> function.


### -field pfnHsSetShader

A pointer to the <a href="https://msdn.microsoft.com/ee70f44c-f160-4fd1-971d-9a4f8b9bd906">HsSetShader</a> function.


### -field pfnHsSetSamplers

A pointer to the <a href="https://msdn.microsoft.com/7aeb4bbc-7405-4795-afdd-d20def3c2c9c">HsSetSamplers</a> function.


### -field pfnHsSetConstantBuffers

A pointer to the <a href="https://msdn.microsoft.com/bbb89a0f-4f46-4397-8c13-9c8a7fd139b1">HsSetConstantBuffers</a> function.


### -field pfnDsSetShaderResources

A pointer to the <a href="https://msdn.microsoft.com/4e108415-4259-4382-8971-63c879f079e7">DsSetShaderResources</a> function.


### -field pfnDsSetShader

A pointer to the <a href="https://msdn.microsoft.com/3824f8b1-d3ee-45be-991f-196ef6eec9c3">DsSetShader</a> function.


### -field pfnDsSetSamplers

A pointer to the <a href="https://msdn.microsoft.com/1d398a7f-9f1b-42bc-862f-457ebbd41761">DsSetSamplers</a> function.


### -field pfnDsSetConstantBuffers

A pointer to the <a href="https://msdn.microsoft.com/02aebbf1-2a27-4f30-a03e-84385f61d486">DsSetConstantBuffers</a> function.


### -field pfnCreateHullShader

A pointer to the <a href="https://msdn.microsoft.com/7fe647cf-37b0-427e-9e16-664bdd365ea6">CreateHullShader</a> function.


### -field pfnCreateDomainShader

A pointer to the <a href="https://msdn.microsoft.com/534c292a-b3ef-41aa-868a-f5e57b90d789">CreateDomainShader</a> function.


### -field pfnCheckDeferredContextHandleSizes

A pointer to the <a href="https://msdn.microsoft.com/0ddaec86-79e6-4d09-8403-6588b35f8b0f">CheckDeferredContextHandleSizes</a> function.


### -field pfnCalcDeferredContextHandleSize

A pointer to the <a href="https://msdn.microsoft.com/d26c26ef-be8e-434a-b3d3-623ed539c541">CalcDeferredContextHandleSize</a> function.


### -field pfnCalcPrivateDeferredContextSize

A pointer to the <a href="https://msdn.microsoft.com/282898b1-45e1-4d85-9ab7-fd400623bdc5">CalcPrivateDeferredContextSize</a> function.


### -field pfnCreateDeferredContext

A pointer to the <a href="https://msdn.microsoft.com/464a2291-55c8-4e51-ba08-219ce426d038">CreateDeferredContext</a> function.


### -field pfnAbandonCommandList

A pointer to the <a href="https://msdn.microsoft.com/fc8347da-25ac-47ea-b482-61b7873ca5bc">AbandonCommandList</a> function.


### -field pfnCalcPrivateCommandListSize

A pointer to the <a href="https://msdn.microsoft.com/04725df2-6373-4e04-862e-d533363af00b">CalcPrivateCommandListSize</a> function.


### -field pfnCreateCommandList

A pointer to the <a href="https://msdn.microsoft.com/583bde52-ba21-44ce-9f48-8ace6f7a70cc">CreateCommandList</a> function.


### -field pfnDestroyCommandList

A pointer to the <a href="https://msdn.microsoft.com/9f03c193-f017-4189-a082-908e28a2e9f7">DestroyCommandList</a> function.


### -field pfnCalcPrivateTessellationShaderSize

A pointer to the <a href="https://msdn.microsoft.com/604d7475-4696-429e-a645-781931509bb6">CalcPrivateTessellationShaderSize</a> function.


### -field pfnPsSetShaderWithIfaces

A pointer to the <a href="https://msdn.microsoft.com/8d8d4449-1770-4a57-b8b9-e1cfc64b96cb">PsSetShaderWithIfaces</a> function.


### -field pfnVsSetShaderWithIfaces

A pointer to the <a href="https://msdn.microsoft.com/cc360e57-8c0a-441a-a072-7dc792ce201c">VsSetShaderWithIfaces</a> function.


### -field pfnGsSetShaderWithIfaces

A pointer to the <a href="https://msdn.microsoft.com/f1db3ed8-7621-4d3a-820d-f50298967404">GsSetShaderWithIfaces</a> function.


### -field pfnHsSetShaderWithIfaces

A pointer to the <a href="https://msdn.microsoft.com/c0dd4504-33d3-4a49-ac4e-169375f81430">HsSetShaderWithIfaces</a> function.


### -field pfnDsSetShaderWithIfaces

A pointer to the <a href="https://msdn.microsoft.com/fce9447a-459d-4446-9764-5b7daedce041">DsSetShaderWithIfaces</a> function.


### -field pfnCsSetShaderWithIfaces

A pointer to the <a href="https://msdn.microsoft.com/2e7170e8-2b77-45a7-9ff5-834452c13ddf">CsSetShaderWithIfaces</a> function.


### -field pfnCreateComputeShader

A pointer to the <a href="https://msdn.microsoft.com/e62ad086-f652-4e2c-bc2d-f1ccb197f01e">CreateComputeShader</a> function.


### -field pfnCsSetShader

A pointer to the <a href="https://msdn.microsoft.com/ab689c60-3099-4d69-a7e2-5edfb623cbc3">CsSetShader</a> function.


### -field pfnCsSetShaderResources

A pointer to the <a href="https://msdn.microsoft.com/29570c3b-eb3b-4d8f-b471-8f3ea6226e23">CsSetShaderResources</a> function.


### -field pfnCsSetSamplers

A pointer to the <a href="https://msdn.microsoft.com/7bf05fb6-e959-464a-9e6b-74c568d1d88c">CsSetSamplers</a> function.


### -field pfnCsSetConstantBuffers

A pointer to the <a href="https://msdn.microsoft.com/159ee0ac-7ddf-4ffd-a07f-3d58130b90e8">CsSetConstantBuffers</a> function.


### -field pfnCalcPrivateUnorderedAccessViewSize

A pointer to the <a href="https://msdn.microsoft.com/6aca5d33-c8c6-4c6b-a66a-e28a958cbc2e">CalcPrivateUnorderedAccessViewSize</a> function.


### -field pfnCreateUnorderedAccessView

A pointer to the <a href="https://msdn.microsoft.com/c5a258e7-6645-46bb-ab2c-a1c8f5e593b7">CreateUnorderedAccessView</a> function.


### -field pfnDestroyUnorderedAccessView

A pointer to the <a href="https://msdn.microsoft.com/1bce3519-f333-4b47-b29b-bde1b5c3005c">DestroyUnorderedAccessView</a> function.


### -field pfnClearUnorderedAccessViewUint

A pointer to the <a href="https://msdn.microsoft.com/7cdc81a9-e468-4da8-bc32-9e9cea1fd60d">ClearUnorderedAccessViewUint</a> function.


### -field pfnClearUnorderedAccessViewFloat

A pointer to the <a href="https://msdn.microsoft.com/31734efd-0c17-4476-918d-942c015072bd">ClearUnorderedAccessViewFloat</a> function.


### -field pfnCsSetUnorderedAccessViews

A pointer to the <a href="https://msdn.microsoft.com/ab8c529b-19e2-4a2a-af68-0e3998829788">CsSetUnorderedAccessViews</a> function.


### -field pfnDispatch

A pointer to the <a href="https://msdn.microsoft.com/6fbbf05a-efb0-4f24-8811-b87141cf2daa">Dispatch</a> function.


### -field pfnDispatchIndirect

A pointer to the <a href="https://msdn.microsoft.com/0c818515-163f-48ba-ad57-f4405672c98f">DispatchIndirect</a> function.


### -field pfnSetResourceMinLOD

A pointer to the <a href="https://msdn.microsoft.com/a54b2fa7-c0c2-42b7-ae89-7984282d4af4">SetResourceMinLOD</a> function.


### -field pfnCopyStructureCount

A pointer to the <a href="https://msdn.microsoft.com/39f20ff3-859f-4933-8be0-e2bb7c05e7e1">CopyStructureCount</a> function.


### -field pfnRecycleCommandList

A pointer to the <a href="https://msdn.microsoft.com/4cff7f3d-ba13-4389-bafc-edffc0697ce9">RecycleCommandList</a> function.


### -field pfnRecycleCreateCommandList

A pointer to the <a href="https://msdn.microsoft.com/c387545e-2891-401d-b7ca-ee7549a52603">RecycleCreateCommandList</a> function.


### -field pfnRecycleCreateDeferredContext

A pointer to the <a href="https://msdn.microsoft.com/c9e08048-683a-4f43-b3b8-1914c2933a5c">RecycleCreateDeferredContext</a> function.


### -field pfnRecycleDestroyCommandList

 


### -field pfnDiscard

A pointer to the <a href="https://msdn.microsoft.com/F3EC7AAE-9DB8-43A1-B756-5F5C91F8372E">Discard</a> function.


### -field pfnAssignDebugBinary

A pointer to the <a href="https://msdn.microsoft.com/eb1e3c27-71c1-4920-9aa4-3253306fa3f4">AssignDebugBinary</a> function.


### -field pfnDynamicConstantBufferMapNoOverwrite

 


### -field pfnCheckDirectFlipSupport

A pointer to the <a href="https://msdn.microsoft.com/BB909041-0194-4828-ACA2-E3F6B1974DBB">CheckDirectFlipSupport</a> function.


### -field pfnClearView

A pointer to the <a href="https://msdn.microsoft.com/c3cc08ea-22db-4fae-a180-76f3babd1c5c">ClearView</a> function.


### -field pfnUpdateTileMappings

A pointer to the <a href="https://msdn.microsoft.com/1C8FC920-145F-4AE9-B049-F6BDAE29D1F1">UpdateTileMappings</a> function.


### -field pfnCopyTileMappings

A pointer to the <a href="https://msdn.microsoft.com/CB2CE5E7-DDD4-4782-BB91-67A2C562A975">CopyTileMappings</a> function.


### -field pfnCopyTiles

A pointer to the <a href="https://msdn.microsoft.com/8DA0FF6C-CA2C-4943-93C3-BFC3773617CC">CopyTiles</a> function.


### -field pfnUpdateTiles

A pointer to the <a href="https://msdn.microsoft.com/4891AB01-DE51-4B32-AA52-5619E86CC474">UpdateTiles</a> function.


### -field pfnTiledResourceBarrier

A pointer to the <a href="https://msdn.microsoft.com/9A2E9B3F-13E4-48D7-A3F3-E7CDCDD1E0CC">TiledResourceBarrier</a> function.


### -field pfnGetMipPacking

A pointer to the <a href="https://msdn.microsoft.com/8AF361B5-279D-4525-AD98-843A4A746201">GetMipPacking</a> function.


### -field pfnResizeTilePool

A pointer to the <a href="https://msdn.microsoft.com/184EF418-1B1E-4A10-8F10-1331DF99DCBD">ResizeTilePool</a> function.


### -field pfnSetMarker

A pointer to the <a href="https://msdn.microsoft.com/BE618B0C-18E7-4B2B-87EB-172DAD9BCE15">SetMarker</a> function.


### -field pfnSetMarkerMode

A pointer to the <a href="https://msdn.microsoft.com/18B13509-7692-4336-937C-264B31A6FB78">SetMarkerMode</a> function.


### -field pfnSetHardwareProtection

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn906369">SetHardwareProtection</a> function.


### -field pfnCalcPrivateShaderResourceViewSizeWDDM2_0

 


### -field pfnCreateShaderResourceViewWDDM2_0

 


### -field pfnCalcPrivateRenderTargetViewSizeWDDM2_0

 


### -field pfnCreateRenderTargetViewWDDM2_0

 


### -field pfnCalcPrivateQuerySizeWDDM2_0

 


### -field pfnCreateQueryWDDM2_0

 


### -field pfnCalcPrivateUnorderedAccessViewSizeWDDM2_0

 


### -field pfnCreateUnorderedAccessViewWDDM2_0

 


### -field pfnFlushWDDM2_0

 


### -field pfnGetResourceLayout

 



