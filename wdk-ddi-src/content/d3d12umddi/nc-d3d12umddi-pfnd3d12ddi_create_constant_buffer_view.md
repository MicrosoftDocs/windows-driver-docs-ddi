---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW
title: PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW
author: windows-driver-content
description: 
ms.assetid: 20f24353-affc-4862-ba13-e3bfc2c0a74d
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
-	PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW
product: Windows
targetos: Windows
---

# PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW Pfnd3d12ddiCreateConstantBufferView; 

// Definition

VOID Pfnd3d12ddiCreateConstantBufferView 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDI_CONSTANT_BUFFER_VIEW_DESC *
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

PFND3D12DDI_CREATE_CONSTANT_BUFFER_VIEW 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 
### -param DestDescriptor: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also