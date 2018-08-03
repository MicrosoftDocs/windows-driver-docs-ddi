---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYBLENDSTATE
title: PFND3D12DDI_DESTROYBLENDSTATE
author: windows-driver-content
description: 
ms.assetid: eb4b3ebd-be63-41cf-af25-9c58ffe69deb
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
-	PFND3D12DDI_DESTROYBLENDSTATE
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_DESTROYBLENDSTATE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_DESTROYBLENDSTATE Pfnd3d12ddiDestroyblendstate; 

// Definition

VOID Pfnd3d12ddiDestroyblendstate 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HBLENDSTATE
)
{...}

PFND3D12DDI_DESTROYBLENDSTATE 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HBLENDSTATE: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also