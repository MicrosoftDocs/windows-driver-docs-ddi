---
UID: NS:d3d10umddi.D3D10DDI_CORELAYER_DEVICECALLBACKS
title: D3D10DDI_CORELAYER_DEVICECALLBACKS (d3d10umddi.h)
description: The D3D10DDI_CORELAYER_DEVICECALLBACKS structure contains Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.
old-location: display\d3d10ddi_corelayer_devicecallbacks.htm
ms.assetid: cced2221-7e8c-432a-9963-3b1de67037a3
ms.date: 05/10/2018
ms.keywords: D3D10DDI_CORELAYER_DEVICECALLBACKS, D3D10DDI_CORELAYER_DEVICECALLBACKS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_4c7782a0-4963-4f18-802e-98c8eb39c1a1.xml, d3d10umddi/D3D10DDI_CORELAYER_DEVICECALLBACKS, display.d3d10ddi_corelayer_devicecallbacks
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10DDI_CORELAYER_DEVICECALLBACKS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- D3D10DDI_CORELAYER_DEVICECALLBACKS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDI_CORELAYER_DEVICECALLBACKS
---

# D3D10DDI_CORELAYER_DEVICECALLBACKS structure


## -description


The D3D10DDI_CORELAYER_DEVICECALLBACKS structure contains Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.


## -struct-fields




### -field pfnSetErrorCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, which the driver uses to send errors back to the Direct3D 10 runtime because many of the driver's functions (in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>) return void.


### -field pfnStateVsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_vs_constbuf_cb">pfnStateVsConstBufCb</a> function.


### -field pfnStatePsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ps_srv_cb">pfnStatePsSrvCb</a> function.


### -field pfnStatePsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ps_shader_cb">pfnStatePsShaderCb</a> function.


### -field pfnStatePsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ps_sampler_cb">pfnStatePsSamplerCb</a> function.


### -field pfnStateVsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_vs_shader_cb">pfnStateVsShaderCb</a> function.


### -field pfnStatePsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ps_constbuf_cb">pfnStatePsConstBufCb</a> function.


### -field pfnStateIaInputLayoutCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ia_inputlayout_cb">pfnStateIaInputLayoutCb</a> function.


### -field pfnStateIaVertexBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ia_vertexbuf_cb">pfnStateIaVertexBufCb</a> function. 


### -field pfnStateIaIndexBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ia_indexbuf_cb">pfnStateIaIndexBufCb</a> function. 


### -field pfnStateGsConstBufCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_gs_constbuf_cb">pfnStateGsConstBufCb</a> function. 


### -field pfnStateGsShaderCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_gs_shader_cb">pfnStateGsShaderCb</a> function. 


### -field pfnStateIaPrimitiveTopologyCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_ia_primitive_topology_cb">pfnStateIaPrimitiveTopologyCb</a> function. 


### -field pfnStateVsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_vs_srv_cb">pfnStateVsSrvCb</a> function. 


### -field pfnStateVsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_vs_sampler_cb">pfnStateVsSamplerCb</a> function. 


### -field pfnStateGsSrvCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_gs_srv_cb">pfnStateGsSrvCb</a> function. 


### -field pfnStateGsSamplerCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_gs_sampler_cb">pfnStateGsSamplerCb</a> function. 


### -field pfnStateOmRenderTargetsCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_om_rendertargets_cb">pfnStateOmRenderTargetsCb</a> function. 


### -field pfnStateOmBlendStateCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_om_blendstate_cb">pfnStateOmBlendStateCb</a> function. 


### -field pfnStateOmDepthStateCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_om_depthstate_cb">pfnStateOmDepthStateCb</a> function. 


### -field pfnStateRsRastStateCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_rs_raststate_cb">pfnStateRsRastStateCb</a> function. 


### -field pfnStateSoTargetsCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_so_targets_cb">pfnStateSoTargetsCb</a> function. 


### -field pfnStateRsViewportsCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_rs_viewports_cb">pfnStateRsViewportsCb</a> function. 


### -field pfnStateRsScissorCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_rs_scissor_cb">pfnStateRsScissorCb</a> function. 


### -field pfnDisableDeferredStagingResourceDestruction

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_disable_deferred_staging_resource_destruction_cb">pfnDisableDeferredStagingResourceDestruction</a> function. By default, the Direct3D 10 runtime defers the destruction of staging resources until the driver indicates that the hardware no longer requires them. The driver can call this function to disable this feature if the driver does not require the deferred destruction functionality. 


### -field pfnStateTextFilterSizeCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_state_textfiltersize_cb">pfnStateTextFilterSizeCb</a> function. 


## -remarks



Because the Direct3D 10 runtime might change the function pointers dynamically, the user-mode display driver cannot cache the function pointers directly. 

The driver uses the functions with "State" in their name to retrieve the current state of the pipeline. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>
 

 

