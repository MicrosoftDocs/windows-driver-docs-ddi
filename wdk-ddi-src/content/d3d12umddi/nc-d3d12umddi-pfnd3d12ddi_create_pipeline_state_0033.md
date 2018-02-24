---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0033
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0033
author: windows-driver-content
description: Used to create a pipeline state.
old-location: display\pfnd3d12ddi_create_pipeline_state_0033.htm
old-project: display
ms.assetid: F8255544-D5B6-4692-BDC0-EF5A2B856153
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3d12ddi_create_pipeline_state_0033, PFND3D12DDI_CREATE_PIPELINE_STATE_0033 entry point [Display Devices], PFND3D12DDI_CREATE_PIPELINE_STATE_0033, d3d12umddi/PFND3D12DDI_CREATE_PIPELINE_STATE_0033
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
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
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_CREATE_PIPELINE_STATE_0033
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATE_PIPELINE_STATE_0033 callback


## -description


Used to create a pipeline state.


## -prototype


````
HRESULT APIENTRY* PFND3D12DDI_CREATE_PIPELINE_STATE_0033(
             D3D12DDI_HDEVICE                       d3d12ddi_hdevice,
  _In_ const D3D12DDIARG_CREATE_PIPELINE_STATE_0033 *d3d12ddiarg_create_pipeline_state_0033,
             D3D12DDI_HPIPELINESTATE                d3d12ddi_hpipelinestate,
             D3D12DDI_HRTPIPELINESTATE              d3d12ddi_hrtpipelinestate
);
````


## -parameters




### -param D3D12DDI_HDEVICE


### -param *


### -param D3D12DDI_HPIPELINESTATE


### -param D3D12DDI_HRTPIPELINESTATE








#### - d3d12ddi_hdevice


#### - d3d12ddi_hdevice

The hardware device being processed.


#### - d3d12ddi_hpipelinestate

Used to create a pipeline state.


#### - d3d12ddi_hrtpipelinestate

Used to create a pipeline state.


#### - d3d12ddiarg_create_pipeline_state_0033 [in]

The arguments used to create a pipeline state.


## -returns



Returns STATUS_SUCCESS if completed successfully.



