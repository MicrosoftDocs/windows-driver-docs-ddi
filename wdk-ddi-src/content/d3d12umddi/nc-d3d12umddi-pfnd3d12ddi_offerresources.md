---
UID: NC:d3d12umddi.PFND3D12DDI_OFFERRESOURCES
title: PFND3D12DDI_OFFERRESOURCES
author: windows-driver-content
description: 
ms.assetid: 794a29be-a6e8-4548-9de8-8230cb781cf8
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
-	PFND3D12DDI_OFFERRESOURCES
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_OFFERRESOURCES callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_OFFERRESOURCES Pfnd3d12ddiOfferresources; 

// Definition

HRESULT Pfnd3d12ddiOfferresources 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OFFERRESOURCES *
)
{...}

PFND3D12DDI_OFFERRESOURCES 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also