---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
title: PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
author: windows-driver-content
description: 
ms.assetid: 40e47e56-5a99-431d-b821-a610a8c66601
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
-	PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
product: Windows
targetos: Windows
---

# PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 Pfnd3d12ddiCalcSerializedLibrarySize0010; 

// Definition

SIZE_T Pfnd3d12ddiCalcSerializedLibrarySize0010 
(
	D3D12DDI_HDEVICE hDevice
	D3D12DDI_HPIPELINELIBRARY hLibrary
)
{...}

PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 


```

## -parameters

### -param hDevice: 
### -param hLibrary: 



## -returns

Returns SIZE_T that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also