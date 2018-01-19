---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0021
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0021
author: windows-driver-content
description: The pfnCreatePipelineState callback function creates a pipeline state.
old-location: display\pfnd3d12ddi_create_pipeline_state_0021.htm
old-project: display
ms.assetid: 08C19E55-7DD7-4BDF-8C9A-A2E1B973AFEC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnCreatePipelineState
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATE_PIPELINE_STATE_0021 callback



## -description
The <i>pfnCreatePipelineState</i> callback function creates a pipeline state.



## -prototype

````
PFND3D12DDI_CREATE_PIPELINE_STATE_0021 pfnCreatePipelineState;

HRESULT APIENTRY* pfnCreatePipelineState(
             D3D12DDI_HDEVICE                       hDevice,
  _In_ const D3D12DDIARG_CREATE_PIPELINE_STATE_0010 *CreatePipelineState,
             D3D12DDI_HPIPELINESTATE                hPipelineState,
             D3D12DDI_HRTPIPELINESTATE              hRTPipelineState
)
{ ... }
````


## -parameters

### -param hDevice 

The handle of a device. 


### -param CreatePipelineState [in]

A value used to create a pipeline state.


### -param hPipelineState 

The handle of a pipeline state. 


### -param hRTPipelineState 

The handle of the pipeline state for the driver to use when it calls back into the runtime.


## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
Access this function by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_device_funcs_core_0021.md">D3D12DDI_DEVICE_FUNCS_CORE_0021</a> structure.</p>