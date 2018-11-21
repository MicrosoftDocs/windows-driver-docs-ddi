---
UID: NC:d3dkmthk.PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID
title: PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID
author: windows-driver-content
description: Pfnd3dkmtGetsharedresourceadapterluid maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.
ms.assetid: 1174993c-ffbb-449f-8bee-6ac2ad947dd0
ms.date: 10/19/2018
ms.topic: callback
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
-	PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID callback function

## -description

Pfnd3dkmtGetsharedresourceadapterluid maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID Pfnd3dkmtGetsharedresourceadapterluid; 

// Definition

NTSTATUS Pfnd3dkmtGetsharedresourceadapterluid 
(
	D3DKMT_GETSHAREDRESOURCEADAPTERLUID *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GETSHAREDRESOURCEADAPTERLUID](ns-d3dkmthk-_d3dkmt_getsharedresourceadapterluid.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
