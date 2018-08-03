---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKSUBRESOURCEINFO
title: PFND3D12DDI_CHECKSUBRESOURCEINFO
author: windows-driver-content
description: 
ms.assetid: d8285aa5-1eec-425b-9cc5-28fa2e14b521
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
-	PFND3D12DDI_CHECKSUBRESOURCEINFO
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_CHECKSUBRESOURCEINFO callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CHECKSUBRESOURCEINFO Pfnd3d12ddiChecksubresourceinfo; 

// Definition

VOID Pfnd3d12ddiChecksubresourceinfo 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HRESOURCE
	UINT Subresource
	D3D12DDI_SUBRESOURCE_INFO *
)
{...}

PFND3D12DDI_CHECKSUBRESOURCEINFO 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HRESOURCE: 
### -param Subresource: 
### -param *: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also