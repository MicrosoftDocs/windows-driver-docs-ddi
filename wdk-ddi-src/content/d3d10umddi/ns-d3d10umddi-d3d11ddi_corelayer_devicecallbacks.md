---
UID: NS:d3d10umddi.D3D11DDI_CORELAYER_DEVICECALLBACKS
title: D3D11DDI_CORELAYER_DEVICECALLBACKS (d3d10umddi.h)
description: The D3D11DDI_CORELAYER_DEVICECALLBACKS structure contains Microsoft Direct3D 11 runtime callback functions that the user-mode display driver can use.
old-location: display\d3d11ddi_corelayer_devicecallbacks.htm
ms.assetid: 7a10b7e0-b062-4ec9-9883-7042f6e55505
ms.date: 05/10/2018
ms.keywords: D3D11DDI_CORELAYER_DEVICECALLBACKS, D3D11DDI_CORELAYER_DEVICECALLBACKS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_182fd279-98be-4418-b7ca-658d038cb39a.xml, d3d10umddi/D3D11DDI_CORELAYER_DEVICECALLBACKS, display.d3d11ddi_corelayer_devicecallbacks
f1_keywords:
 - "d3d10umddi/D3D11DDI_CORELAYER_DEVICECALLBACKS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_CORELAYER_DEVICECALLBACKS is supported beginning with the Windows 7 operating system.
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
- D3D11DDI_CORELAYER_DEVICECALLBACKS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDI_CORELAYER_DEVICECALLBACKS
---

# D3D11DDI_CORELAYER_DEVICECALLBACKS structure


## -description


The D3D11DDI_CORELAYER_DEVICECALLBACKS structure contains Microsoft Direct3D 11 runtime callback functions that the user-mode display driver can use.


## -struct-fields




### -field pfnSetErrorCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, which the driver uses to send errors back to the Direct3D 11 runtime because many of the driver's functions (in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>) return void.


### -field pfnStateVsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_vs_constbuf_cb">pfnStateVsConstBufCb</a> function.


### -field pfnStatePsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ps_srv_cb">pfnStatePsSrvCb</a> function.


### -field pfnStatePsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ps_shader_cb">pfnStatePsShaderCb</a> function.


### -field pfnStatePsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ps_sampler_cb">pfnStatePsSamplerCb</a> function.


### -field pfnStateVsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_vs_shader_cb">pfnStateVsShaderCb</a> function.


### -field pfnStatePsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ps_constbuf_cb">pfnStatePsConstBufCb</a> function.


### -field pfnStateIaInputLayoutCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ia_inputlayout_cb">pfnStateIaInputLayoutCb</a> function.


### -field pfnStateIaVertexBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ia_vertexbuf_cb">pfnStateIaVertexBufCb</a> function. 


### -field pfnStateIaIndexBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ia_indexbuf_cb">pfnStateIaIndexBufCb</a> function. 


### -field pfnStateGsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_gs_constbuf_cb">pfnStateGsConstBufCb</a> function. 


### -field pfnStateGsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_gs_shader_cb">pfnStateGsShaderCb</a> function. 


### -field pfnStateIaPrimitiveTopologyCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ia_primitive_topology_cb">pfnStateIaPrimitiveTopologyCb</a> function. 


### -field pfnStateVsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_vs_srv_cb">pfnStateVsSrvCb</a> function. 


### -field pfnStateVsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_vs_sampler_cb">pfnStateVsSamplerCb</a> function. 


### -field pfnStateGsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_gs_srv_cb">pfnStateGsSrvCb</a> function. 


### -field pfnStateGsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_gs_sampler_cb">pfnStateGsSamplerCb</a> function. 


### -field pfnStateOmRenderTargetsCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_om_rendertargets_cb">pfnStateOmRenderTargetsCb</a> function. 


### -field pfnStateOmBlendStateCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_om_blendstate_cb">pfnStateOmBlendStateCb</a> function. 


### -field pfnStateOmDepthStateCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_om_depthstate_cb">pfnStateOmDepthStateCb</a> function. 


### -field pfnStateRsRastStateCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_rs_raststate_cb">pfnStateRsRastStateCb</a> function. 


### -field pfnStateSoTargetsCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_so_targets_cb">pfnStateSoTargetsCb</a> function. 


### -field pfnStateRsViewportsCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_rs_viewports_cb">pfnStateRsViewportsCb</a> function. 


### -field pfnStateRsScissorCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_rs_scissor_cb">pfnStateRsScissorCb</a> function. 


### -field pfnDisableDeferredStagingResourceDestruction

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_disable_deferred_staging_resource_destruction_cb">pfnDisableDeferredStagingResourceDestruction</a> function. By default, the Direct3D 10 runtime defers the destruction of staging resources until the driver indicates that the hardware no longer requires them. The driver can call this function to disable this feature if the driver does not require the deferred destruction functionality. 


### -field pfnStateTextFilterSizeCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_textfiltersize_cb">pfnStateTextFilterSizeCb</a> function. 

<b>The following functions are supported beginning with Windows 7:  </b>


### -field pfnStateHsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_hs_srv_cb">pfnStateHsSrvCb</a> function. 


### -field pfnStateHsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_hs_shader_cb">pfnStateHsShaderCb</a> function. 


### -field pfnStateHsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_hs_sampler_cb">pfnStateHsSamplerCb</a> function. 


### -field pfnStateHsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_hs_constbuf_cb">pfnStateHsConstBufCb</a> function. 


### -field pfnStateDsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_ds_srv_cb">pfnStateDsSrvCb</a> function. 


### -field pfnStateDsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_ds_shader_cb">pfnStateDsShaderCb</a> function. 


### -field pfnStateDsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_ds_sampler_cb">pfnStateDsSamplerCb</a> function. 


### -field pfnStateDsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_ds_constbuf_cb">pfnStateDsConstBufCb</a> function. 


### -field pfnPerformAmortizedProcessingCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_perform_amortized_processing_cb">pfnPerformAmortizedProcessingCb</a> function. 


### -field pfnStateCsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_cs_srv_cb">pfnStateCsSrvCb</a> function. 


### -field pfnStateCsUavCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_cs_uav_cb">pfnStateCsUavCb</a> function. 


### -field pfnStateCsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_cs_shader_cb">pfnStateCsShaderCb</a> function. 


### -field pfnStateCsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_cs_sampler_cb">pfnStateCsSamplerCb</a> function. 


### -field pfnStateCsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_state_cs_constbuf_cb">pfnStateCsConstBufCb</a> function. 


## -remarks



Because the Direct3D 11 runtime might change the function pointers dynamically, the user-mode display driver cannot cache the function pointers directly. 

The driver uses the functions with "State" in their name to retrieve the current state of the pipeline. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>
 

 

