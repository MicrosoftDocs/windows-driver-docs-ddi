---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_COMMAND_SIGNATURE
title: PFND3D12DDI_DESTROY_COMMAND_SIGNATURE
author: windows-driver-content
description: 
ms.assetid: c114db95-eabb-4bd0-af4f-d4b72032442b
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
-	PFND3D12DDI_DESTROY_COMMAND_SIGNATURE
product: Windows
targetos: Windows
---

# PFND3D12DDI_DESTROY_COMMAND_SIGNATURE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_DESTROY_COMMAND_SIGNATURE Pfnd3d12ddiDestroyCommandSignature; 

// Definition

VOID Pfnd3d12ddiDestroyCommandSignature 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HCOMMANDSIGNATURE
)
{...}

PFND3D12DDI_DESTROY_COMMAND_SIGNATURE 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HCOMMANDSIGNATURE: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also