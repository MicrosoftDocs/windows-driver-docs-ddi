---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0021
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0021 (d3d12umddi.h)
description: The pfnCreatePipelineState callback function creates a pipeline state.
old-location: display\pfnd3d12ddi_create_pipeline_state_0021.htm
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_CREATE_PIPELINE_STATE_0021 callback function"]
ms.keywords: PFND3D12DDI_CREATE_PIPELINE_STATE_0021, PFND3D12DDI_CREATE_PIPELINE_STATE_0021 callback, d3d12umddi/pfnCreatePipelineState, display.pfnd3d12ddi_create_pipeline_state_0021, pfnCreatePipelineState, pfnCreatePipelineState callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_CREATE_PIPELINE_STATE_0021
 - d3d12umddi/PFND3D12DDI_CREATE_PIPELINE_STATE_0021
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - pfnCreatePipelineState
product:
 - Windows
---

# PFND3D12DDI_CREATE_PIPELINE_STATE_0021 callback function


## -description

The <i>pfnCreatePipelineState</i> callback function creates a pipeline state.

## -parameters

### -param Arg1

*hDevice*

A handle to the display device (graphics context).

### -param Arg2

CreatePipelineState [in]

A value used to create a pipeline state.

### -param Arg3

hRTPipelineState

The handle of the pipeline state for the driver to use when it calls back into the runtime.

### -param Arg4

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

Access this function by using the <a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_device_funcs_core_0021">D3D12DDI_DEVICE_FUNCS_CORE_0021</a> structure.
