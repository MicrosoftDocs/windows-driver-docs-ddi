---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0033
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0033
author: windows-driver-content
description: Used to create a pipeline state.
old-location: display\pfnd3d12ddi_create_pipeline_state_0033.htm
old-project: display
ms.assetid: F8255544-D5B6-4692-BDC0-EF5A2B856153
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
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
req.alt-api: PFND3D12DDI_CREATE_PIPELINE_STATE_0033
req.alt-loc: d3d12umddi.h
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

### -param d3d12ddi_hdevice 

The hardware device being processed.


### -param d3d12ddiarg_create_pipeline_state_0033 [in]

The arguments used to create a pipeline state.


### -param d3d12ddi_hpipelinestate 

Used to create a pipeline state.


### -param d3d12ddi_hrtpipelinestate 

Used to create a pipeline state.


## -returns
Returns STATUS_SUCCESS if completed successfully.


## -remarks
