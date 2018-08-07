---
UID: NC:d3d12umddi.PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES
title: PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES
author: windows-driver-content
description: 
ms.assetid: 3387f063-96f5-4d77-b006-924738808d51
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
-	PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES Pfnd3d12ddiGetDescriptorSizeInBytes; 

// Definition

UINT Pfnd3d12ddiGetDescriptorSizeInBytes 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_DESCRIPTOR_HEAP_TYPE
)
{...}

PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_DESCRIPTOR_HEAP_TYPE: 



## -returns

Returns UINT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also