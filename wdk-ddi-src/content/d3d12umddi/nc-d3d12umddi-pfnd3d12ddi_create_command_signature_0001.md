---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001
title: PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001
author: windows-driver-content
description: 
ms.assetid: 467a206c-9fe2-41c0-a264-05a80be53a6c
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
-	PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001 Pfnd3d12ddiCreateCommandSignature0001; 

// Definition

HRESULT Pfnd3d12ddiCreateCommandSignature0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001 *
	 D3D12DDI_HCOMMANDSIGNATURE
)
{...}

PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 
### -param D3D12DDI_HCOMMANDSIGNATURE: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also