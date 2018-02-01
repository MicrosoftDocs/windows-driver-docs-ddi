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
ms.keywords: display.pfnd3d12ddi_create_pipeline_state_0021, pfnCreatePipelineState callback function [Display Devices], pfnCreatePipelineState, PFND3D12DDI_CREATE_PIPELINE_STATE_0021, PFND3D12DDI_CREATE_PIPELINE_STATE_0021, d3d12umddi/pfnCreatePipelineState
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
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnCreatePipelineState
product: Windows
targetos: Windows
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




### -param D3D12DDI_HDEVICE



### -param *



### -param D3D12DDI_HPIPELINESTATE



### -param D3D12DDI_HRTPIPELINESTATE






#### - CreatePipelineState [in]

A value used to create a pipeline state.


#### - hDevice

The handle of a device. 


#### - hPipelineState

The handle of a pipeline state. 


#### - hRTPipelineState

The handle of the pipeline state for the driver to use when it calls back into the runtime.


## -returns


If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -remarks


Access this function by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_device_funcs_core_0021.md">D3D12DDI_DEVICE_FUNCS_CORE_0021</a> structure.


