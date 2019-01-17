---
UID: NC:d3dkmthk.PFND3DKMT_PINDIRECTFLIPRESOURCES
title: PFND3DKMT_PINDIRECTFLIPRESOURCES
description: The PFND3DKMT_PINDIRECTFLIPRESOURCES callback function pins direct flip resources.
ms.assetid: 7cb8aa84-fd33-4667-af4d-6ceb20e5edf5
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
- PFND3DKMT_PINDIRECTFLIPRESOURCES
- D3DKMTPinDirectFlipResources
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_PINDIRECTFLIPRESOURCES callback function

## -description

The PFND3DKMT_PINDIRECTFLIPRESOURCES callback function pins direct flip resources. 

## -prototype

```cpp
//Declaration

PFND3DKMT_PINDIRECTFLIPRESOURCES Pfnd3dkmtPindirectflipresources; 

// Definition

NTSTATUS Pfnd3dkmtPindirectflipresources 
(
	const D3DKMT_PINDIRECTFLIPRESOURCES *
)
{...}

```

## -parameters

### -param * 

*\_In\_* *pResources*

Pointer to a [D3DKMT_PINDIRECTFLIPRESOURCES](ns-d3dkmthk-_d3dkmt_pindirectflipresources.md) structure.

## -returns

Returns NTSTATUS.

## -remarks

## -see-also

[D3DKMT_PINDIRECTFLIPRESOURCES](ns-d3dkmthk-_d3dkmt_pindirectflipresources.md)
