---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS
title: PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS
author: windows-driver-content
description: 
ms.assetid: e54aa0b0-c2ef-44db-9053-3ceeb71cf9a8
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
-	PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS
product: Windows
targetos: Windows
---

# PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS Pfnd3d12ddiCheckresourcevirtualaddress; 

// Definition

D3D12DDI_GPU_VIRTUAL_ADDRESS Pfnd3d12ddiCheckresourcevirtualaddress 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HRESOURCE: 



## -returns

Returns D3D12DDI_GPU_VIRTUAL_ADDRESS that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also