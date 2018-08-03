---
UID: NC:d3d12umddi.PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010
title: PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010
author: windows-driver-content
description: 
ms.assetid: b7f4ac02-7138-420f-b633-8f93fd7b5b86
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	d3d12umddi.h
apiname: 
-	PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010 Pfnd3d12ddiAddPipelineStateToLibrary0010; 

// Definition

HRESULT Pfnd3d12ddiAddPipelineStateToLibrary0010 
(
	D3D12DDI_HDEVICE hDevice
	D3D12DDI_HPIPELINELIBRARY hLibrary
	D3D12DDI_HPIPELINESTATE hPipelineState
	UINT PipelineIndex
)
{...}

PFND3D12DDI_ADD_PIPELINE_STATE_TO_LIBRARY_0010 


```

## -parameters

### -param hDevice: 
### -param hLibrary: 
### -param hPipelineState: 
### -param PipelineIndex: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also