---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO
title: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO
author: windows-driver-content
description: 
ms.assetid: d93b90b4-3509-42bf-8ec2-2fc0bd47b2f9
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
-	PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO
product: Windows
targetos: Windows
---

# PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO Pfnd3d12ddiCheckexisitingresourceallocationinfo; 

// Definition

VOID Pfnd3d12ddiCheckexisitingresourceallocationinfo 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HRESOURCE
	D3D12DDI_RESOURCE_ALLOCATION_INFO *
	D3DKMT_HANDLE *phAllocation
)
{...}

PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HRESOURCE: 
### -param *: 
### -param *phAllocation: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also