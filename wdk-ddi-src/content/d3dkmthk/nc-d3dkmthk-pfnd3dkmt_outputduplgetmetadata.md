---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLGETMETADATA
title: PFND3DKMT_OUTPUTDUPLGETMETADATA
author: windows-driver-content
description: The PFND3DKMT_OUTPUTDUPLGETMETADATA callback function gets output duplicate metadata.
ms.assetid: 1fcf334f-ebad-4a39-8357-ecc76ffec8e2
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmthk.h
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_OUTPUTDUPLGETMETADATA
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_OUTPUTDUPLGETMETADATA callback function

## -description

The PFND3DKMT_OUTPUTDUPLGETMETADATA callback function gets output duplicate metadata.

## -prototype

```cpp
//Declaration

PFND3DKMT_OUTPUTDUPLGETMETADATA Pfnd3dkmtOutputduplgetmetadata; 

// Definition

NTSTATUS Pfnd3dkmtOutputduplgetmetadata 
(
	D3DKMT_OUTPUTDUPL_METADATA *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OUTPUTDUPL_METADATA](ns-d3dkmthk-_d3dkmt_outputdupl_metadata.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
