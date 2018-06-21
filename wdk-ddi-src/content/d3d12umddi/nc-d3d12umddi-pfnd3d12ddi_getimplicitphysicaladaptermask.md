---
UID: NC:d3d12umddi.PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK
title: PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK
author: windows-driver-content
description: 
ms.assetid: c9f5b9fc-5d92-4e27-bad2-67bba6d1f7c3
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
-	PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK
product: Windows
targetos: Windows
---

# PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK Pfnd3d12ddiGetimplicitphysicaladaptermask; 

// Definition

UINT Pfnd3d12ddiGetimplicitphysicaladaptermask 
(
	 D3D12DDI_HDEVICE
)
{...}

PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK 


```

## -parameters

### -param D3D12DDI_HDEVICE: 



## -returns

Returns UINT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also