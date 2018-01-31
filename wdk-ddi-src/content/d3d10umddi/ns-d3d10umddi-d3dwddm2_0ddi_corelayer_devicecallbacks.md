---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS
title: D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS
author: windows-driver-content
description: This structure contains the function table for the core layer device callback functions.
old-location: display\d3dwddm2_0ddi_corelayer_devicecallbacks.htm
old-project: display
ms.assetid: A8E60BF8-2DFE-479A-9DA9-C3D9B012EBE9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dwddm2_0ddi_corelayer_devicecallbacks, D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS, d3d10umddi/D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS, D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS
---

# D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS structure


## -description


This structure contains the function table for the core layer device callback functions.


## -syntax


````
typedef struct D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS {
  PFND3D10DDI_SETERROR_CB                                      pfnSetErrorCb;
  PFND3D10DDI_STATE_VS_CONSTBUF_CB                             pfnStateVsConstBufCb;
  PFND3D10DDI_STATE_PS_SRV_CB                                  pfnStatePsSrvCb;
  PFND3D10DDI_STATE_PS_SHADER_CB                               pfnStatePsShaderCb;
  PFND3D10DDI_STATE_PS_SAMPLER_CB                              pfnStatePsSamplerCb;
  PFND3D10DDI_STATE_VS_SHADER_CB                               pfnStateVsShaderCb;
  PFND3D10DDI_STATE_PS_CONSTBUF_CB                             pfnStatePsConstBufCb;
  PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB                          pfnStateIaInputLayoutCb;
  PFND3D10DDI_STATE_IA_VERTEXBUF_CB                            pfnStateIaVertexBufCb;
  PFND3D10DDI_STATE_IA_INDEXBUF_CB                             pfnStateIaIndexBufCb;
  PFND3D10DDI_STATE_GS_CONSTBUF_CB                             pfnStateGsConstBufCb;
  PFND3D10DDI_STATE_GS_SHADER_CB                               pfnStateGsShaderCb;
  PFND3D10DDI_STATE_IA_PRIMITIVE_TOPOLOGY_CB                   pfnStateIaPrimitiveTopologyCb;
  PFND3D10DDI_STATE_VS_SRV_CB                                  pfnStateVsSrvCb;
  PFND3D10DDI_STATE_VS_SAMPLER_CB                              pfnStateVsSamplerCb;
  PFND3D10DDI_STATE_GS_SRV_CB                                  pfnStateGsSrvCb;
  PFND3D10DDI_STATE_GS_SAMPLER_CB                              pfnStateGsSamplerCb;
  PFND3D10DDI_STATE_OM_RENDERTARGETS_CB                        pfnStateOmRenderTargetsCb;
  PFND3D10DDI_STATE_OM_BLENDSTATE_CB                           pfnStateOmBlendStateCb;
  PFND3D10DDI_STATE_OM_DEPTHSTATE_CB                           pfnStateOmDepthStateCb;
  PFND3D10DDI_STATE_RS_RASTSTATE_CB                            pfnStateRsRastStateCb;
  PFND3D10DDI_STATE_SO_TARGETS_CB                              pfnStateSoTargetsCb;
  PFND3D10DDI_STATE_RS_VIEWPORTS_CB                            pfnStateRsViewportsCb;
  PFND3D10DDI_STATE_RS_SCISSOR_CB                              pfnStateRsScissorCb;
  PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB pfnDisableDeferredStagingResourceDestruction;
  PFND3D10DDI_STATE_TEXTFILTERSIZE_CB                          pfnStateTextFilterSizeCb;
  PFND3D11DDI_STATE_HS_SRV_CB                                  pfnStateHsSrvCb;
  PFND3D11DDI_STATE_HS_SHADER_CB                               pfnStateHsShaderCb;
  PFND3D11DDI_STATE_HS_SAMPLER_CB                              pfnStateHsSamplerCb;
  PFND3D11DDI_STATE_HS_CONSTBUF_CB                             pfnStateHsConstBufCb;
  PFND3D11DDI_STATE_DS_SRV_CB                                  pfnStateDsSrvCb;
  PFND3D11DDI_STATE_DS_SHADER_CB                               pfnStateDsShaderCb;
  PFND3D11DDI_STATE_DS_SAMPLER_CB                              pfnStateDsSamplerCb;
  PFND3D11DDI_STATE_DS_CONSTBUF_CB                             pfnStateDsConstBufCb;
  PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB                  pfnPerformAmortizedProcessingCb;
  PFND3D11DDI_STATE_CS_SRV_CB                                  pfnStateCsSrvCb;
  PFND3D11DDI_STATE_CS_UAV_CB                                  pfnStateCsUavCb;
  PFND3D11DDI_STATE_CS_SHADER_CB                               pfnStateCsShaderCb;
  PFND3D11DDI_STATE_CS_SAMPLER_CB                              pfnStateCsSamplerCb;
  PFND3D11DDI_STATE_CS_CONSTBUF_CB                             pfnStateCsConstBufCb;
  PFND3DWDDM2_0DDI_CREATECONTEXT_CB                            pfnCreateContextCb;
  PFND3DWDDM2_0DDI_CREATECONTEXTVIRTUAL_CB                     pfnCreateContextVirtualCb;
} D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS;
````


## -struct-fields




#### - pfnSetErrorCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function.


#### - pfnStateVsConstBufCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_vs_constbuf_cb.md">pfnStateVsConstBufCb</a> function.


#### - pfnStatePsSrvCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ps_srv_cb.md">pfnStatePsSrvCb</a> function.


#### - pfnStatePsShaderCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ps_shader_cb.md">pfnStatePsShaderCb</a> function.


#### - pfnStatePsSamplerCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ps_sampler_cb.md">pfnStatePsSamplerCb</a> function.


#### - pfnStateVsShaderCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_vs_shader_cb.md">pfnStateVsShaderCb</a> function.


#### - pfnStatePsConstBufCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ps_constbuf_cb.md">pfnStatePsConstBufCb</a> function.


#### - pfnStateIaInputLayoutCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ia_inputlayout_cb.md">pfnStateIaInputLayoutCb</a> function.


#### - pfnStateIaVertexBufCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ia_vertexbuf_cb.md">pfnStateIaVertexBufCb</a> function.


#### - pfnStateIaIndexBufCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ia_indexbuf_cb.md">pfnStateIaIndexBufCb</a> function.


#### - pfnStateGsConstBufCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_gs_constbuf_cb.md">pfnStateGsConstBufCb</a> function.


#### - pfnStateGsShaderCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_gs_shader_cb.md">pfnStateGsShaderCb</a> function.


#### - pfnStateIaPrimitiveTopologyCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ia_primitive_topology_cb.md">pfnStateIaPrimitiveTopologyCb</a> function.


#### - pfnStateVsSrvCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_vs_srv_cb.md">pfnStateVsSrvCb</a> function.


#### - pfnStateVsSamplerCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_vs_sampler_cb.md">pfnStateVsSamplerCb</a> function.


#### - pfnStateGsSrvCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_gs_srv_cb.md">pfnStateGsSrvCb</a> function.


#### - pfnStateGsSamplerCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_gs_sampler_cb.md">pfnStateGsSamplerCb</a> function.


#### - pfnStateOmRenderTargetsCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_om_rendertargets_cb.md">pfnStateOmRenderTargetsCb</a> function.


#### - pfnStateOmBlendStateCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_om_blendstate_cb.md">pfnStateOmBlendStateCb</a> function.


#### - pfnStateOmDepthStateCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_om_depthstate_cb.md">pfnStateOmDepthStateCb</a> function.


#### - pfnStateRsRastStateCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_rs_raststate_cb.md">pfnStateRsRastStateCb</a> function.


#### - pfnStateSoTargetsCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_so_targets_cb.md">pfnStateSoTargetsCb</a> function.


#### - pfnStateRsViewportsCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_rs_viewports_cb.md">pfnStateRsViewportsCb</a> function.


#### - pfnStateRsScissorCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_rs_scissor_cb.md">pfnStateRsScissorCb</a> function.


#### - pfnDisableDeferredStagingResourceDestruction

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_disable_deferred_staging_resource_destruction_cb.md">pfnDisableDeferredStagingResourceDestruction</a> function.


#### - pfnStateTextFilterSizeCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_textfiltersize_cb.md">pfnStateTextFilterSizeCb</a> function.


#### - pfnStateHsSrvCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_hs_srv_cb.md">pfnStateHsSrvCb</a> function.


#### - pfnStateHsShaderCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_hs_shader_cb.md">pfnStateHsShaderCb</a> function.


#### - pfnStateHsSamplerCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_hs_sampler_cb.md">pfnStateHsSamplerCb</a> function.


#### - pfnStateHsConstBufCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_hs_constbuf_cb.md">pfnStateHsConstBufCb</a> function.


#### - pfnStateDsSrvCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_ds_srv_cb.md">pfnStateDsSrvCb</a> function.


#### - pfnStateDsShaderCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_ds_shader_cb.md">pfnStateDsShaderCb</a> function.


#### - pfnStateDsSamplerCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_ds_sampler_cb.md">pfnStateDsSamplerCb</a> function.


#### - pfnStateDsConstBufCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_ds_constbuf_cb.md">pfnStateDsConstBufCb</a> function.


#### - pfnPerformAmortizedProcessingCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_perform_amortized_processing_cb.md">pfnPerformAmortizedProcessingCb</a> function.


#### - pfnStateCsSrvCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_cs_srv_cb.md">pfnStateCsSrvCb</a> function.


#### - pfnStateCsUavCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_cs_uav_cb.md">pfnStateCsUavCb</a> function.


#### - pfnStateCsShaderCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_cs_shader_cb.md">pfnStateCsShaderCb</a> function.


#### - pfnStateCsSamplerCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_cs_sampler_cb.md">pfnStateCsSamplerCb</a> function.


#### - pfnStateCsConstBufCb

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_state_cs_constbuf_cb.md">pfnStateCsConstBufCb</a> function.


#### - pfnCreateContextCb

A pointer to the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function.


#### - pfnCreateContextVirtualCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcontextvirtualcb.md">pfnCreateContextVirtualCb</a> function.

