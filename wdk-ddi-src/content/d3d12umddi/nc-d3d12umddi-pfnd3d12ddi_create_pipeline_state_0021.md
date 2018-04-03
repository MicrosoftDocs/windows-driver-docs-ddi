---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0021
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0021
author: windows-driver-content
description: The pfnCreatePipelineState callback function creates a pipeline state.
old-location: display\pfnd3d12ddi_create_pipeline_state_0021.htm
old-project: display
ms.assetid: 08C19E55-7DD7-4BDF-8C9A-A2E1B973AFEC
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_CREATE_PIPELINE_STATE_0021, d3d12umddi/pfnCreatePipelineState, display.pfnd3d12ddi_create_pipeline_state_0021, pfnCreatePipelineState, pfnCreatePipelineState callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnCreatePipelineState
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATE_PIPELINE_STATE_0021 callback


## -description


The <i>pfnCreatePipelineState</i> callback function creates a pipeline state.


## -parameters




### -param Arg1

A handle to the display device (graphics context).

### -param *


### -param Arg2


### -param Arg3








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



Access this function by using the <a href="https://msdn.microsoft.com/4E4C3DB3-9C4C-4BBC-82C4-C5C41C0B818C">D3D12DDI_DEVICE_FUNCS_CORE_0021</a> structure.



