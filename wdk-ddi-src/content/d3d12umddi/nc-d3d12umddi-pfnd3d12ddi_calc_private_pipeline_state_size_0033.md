---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033
title: PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033
author: windows-driver-content
description: Used to calculate the pipeline state size.
old-location: display\pfnd3d12ddi_calc_private_pipeline_state_size_0033_.htm
old-project: display
ms.assetid: C119B295-CBCF-46B3-BC8D-3C8AC058F6D8
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
req.alt-api: PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033
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

# PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033 callback



## -description
Used to calculate the pipeline state size.



## -prototype

````
SIZE_T APIENTRY* PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033 (
             D3D12DDI_HDEVICE                       hDevice,
  _In_ const D3D12DDIARG_CREATE_PIPELINE_STATE_0033 *d3d12ddiarg_create_pipeline_state_0033
);
````


## -parameters

### -param hDevice 

The device being processed.


### -param d3d12ddiarg_create_pipeline_state_0033 [in]

Used to create a pipeline state.


## -returns
The size in bytes of the state size.


## -remarks
