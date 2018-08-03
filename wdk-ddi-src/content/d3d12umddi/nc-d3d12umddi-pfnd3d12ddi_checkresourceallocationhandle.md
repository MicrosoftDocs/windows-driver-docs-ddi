---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE
title: PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE
author: windows-driver-content
description: 
ms.assetid: 627c14f1-f793-40a8-b52d-ba98f90d2d1b
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
-	PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE Pfnd3d12ddiCheckresourceallocationhandle; 

// Definition

D3DKMT_HANDLE Pfnd3d12ddiCheckresourceallocationhandle 
(
	 D3D12DDI_HDEVICE
	 D3D10DDI_HRESOURCE
)
{...}

PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D10DDI_HRESOURCE: 



## -returns

Returns D3DKMT_HANDLE that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also