---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS
title: PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS
author: windows-driver-content
description:
ms.assetid: 50197de3-654f-47d1-9213-d10ac78c0299
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
-	PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function

## -description

Implemented by the client driver to check multi-sample quality levels.

## -prototype

```
//Declaration

PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS Pfnd3d12ddiCheckmultisamplequalitylevels;

// Definition

VOID Pfnd3d12ddiCheckmultisamplequalitylevels
(
	D3D12DDI_HDEVICE hDevice
	DXGI_FORMAT Format
	UINT SampleCount
	D3D12DDI_MULTISAMPLE_QUALITY_LEVEL_FLAGS Flags
	UINT *pNumQualityLevels
)
{...}

PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS


```

## -parameters

### -param hDevice:
### -param Format:
### -param SampleCount:
### -param Flags:
### -param *pNumQualityLevels:



## -returns

Returns VOID.

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.

