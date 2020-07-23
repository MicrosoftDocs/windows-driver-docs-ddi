---
UID: NS:d3d10umddi.D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS
title: D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS (d3d10umddi.h)
description: Specifies core layer device callback functions.
old-location: display\d3dwddm2_2ddi_corelayer_devicecallbacks.htm
ms.assetid: B42DA194-690F-41A6-AC11-71224887A2E4
ms.date: 05/10/2018
keywords: ["D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS structure"]
ms.keywords: D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS, D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS structure [Display Devices], d3d10umddi/D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS, display.d3dwddm2_2ddi_corelayer_devicecallbacks
f1_keywords:
 - "d3d10umddi/D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS"
 - "D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS"
req.header: d3d10umddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS
---

# D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS structure


## -description


Specifies core layer device callback functions. 


## -struct-fields




### -field pfnSetErrorCb

 


### -field pfnStateVsConstBufCb

 


### -field pfnStatePsSrvCb

 


### -field pfnStatePsShaderCb

 


### -field pfnStatePsSamplerCb

 


### -field pfnStateVsShaderCb

 


### -field pfnStatePsConstBufCb

 


### -field pfnStateIaInputLayoutCb

 


### -field pfnStateIaVertexBufCb

 


### -field pfnStateIaIndexBufCb

 


### -field pfnStateGsConstBufCb

 


### -field pfnStateGsShaderCb

 


### -field pfnStateIaPrimitiveTopologyCb

 


### -field pfnStateVsSrvCb

 


### -field pfnStateVsSamplerCb

 


### -field pfnStateGsSrvCb

 


### -field pfnStateGsSamplerCb

 


### -field pfnStateOmRenderTargetsCb

 


### -field pfnStateOmBlendStateCb

 


### -field pfnStateOmDepthStateCb

 


### -field pfnStateRsRastStateCb

 


### -field pfnStateSoTargetsCb

 


### -field pfnStateRsViewportsCb

 


### -field pfnStateRsScissorCb

 


### -field pfnDisableDeferredStagingResourceDestruction

 


### -field pfnStateTextFilterSizeCb

 


### -field pfnStateHsSrvCb

 


### -field pfnStateHsShaderCb

 


### -field pfnStateHsSamplerCb

 


### -field pfnStateHsConstBufCb

 


### -field pfnStateDsSrvCb

 


### -field pfnStateDsShaderCb

 


### -field pfnStateDsSamplerCb

 


### -field pfnStateDsConstBufCb

 


### -field pfnPerformAmortizedProcessingCb

 


### -field pfnStateCsSrvCb

 


### -field pfnStateCsUavCb

 


### -field pfnStateCsShaderCb

 


### -field pfnStateCsSamplerCb

 


### -field pfnStateCsConstBufCb

 


### -field pfnCreateContextCb

 


### -field pfnCreateContextVirtualCb

 


### -field pfnShaderCacheGetValueCb

 
A callback function that gets the shader cache value.

### -field pfnShaderCacheStoreValueCb

A callback function that stores the shader cache value.


### -field pfnShaderCacheAddRefCb

A callback function that adds a reference to the shader cache. 


### -field pfnShaderCacheReleaseCb

A callback function that releases a reference to a cache. 



