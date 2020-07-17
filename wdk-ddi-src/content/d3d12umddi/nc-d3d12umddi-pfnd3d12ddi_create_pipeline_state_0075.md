---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0075
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0075 (d3d12umddi.h)
description: PFND3D12DDI_CREATE_PIPELINE_STATE_0075 is used to create a pipeline state.
ms.assetid: 6145fabe-93af-4a3c-a3bf-625fff6bc656
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CREATE_PIPELINE_STATE_0075 callback function"]
ms.keywords: PFND3D12DDI_CREATE_PIPELINE_STATE_0075, PFND3D12DDI_CREATE_PIPELINE_STATE_0075 entry, PFND3D12DDI_CREATE_PIPELINE_STATE_0075 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CREATE_PIPELINE_STATE_0075, display.pfnd3d12ddi_create_pipeline_state_0075
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
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
 - "d3d12umddi/PFND3D12DDI_CREATE_PIPELINE_STATE_0075"
 - "PFND3D12DDI_CREATE_PIPELINE_STATE_0075"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_PIPELINE_STATE_0075
product:
 - Windows
---

# PFND3D12DDI_CREATE_PIPELINE_STATE_0075 callback function

## -description

**PFND3D12DDI_CREATE_PIPELINE_STATE_0075** is used to create a pipeline state.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a [**D3D12DDIARG_CREATE_PIPELINE_STATE_0075**](ns-d3d12umddi-d3d12ddiarg_create_pipeline_state_0075.md) structure with arguments used to create a pipeline state.

### -param Arg3

Handle to the pipeline state.

### -param Arg4

Handle to the pipeline state for the driver to use when it calls back into the runtime.

## -returns

Returns STATUS_SUCCESS if completed successfully.

## -see-also

[**D3D12DDIARG_CREATE_PIPELINE_STATE_0075**](ns-d3d12umddi-d3d12ddiarg_create_pipeline_state_0075.md)
