---
UID: NC:d3dkmthk.PFND3DKMT_RENDER
title: PFND3DKMT_RENDER
author: windows-driver-content
description: The PFND3DKMT_RENDER callback function submits the current command buffer to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).
ms.assetid: 4eb9114d-9456-41a3-842f-ffa87079fbfa
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
-	PFND3DKMT_RENDER
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_RENDER callback function

## -description

The PFND3DKMT_RENDER callback function submits the current command buffer to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).

## -prototype

```cpp
//Declaration

PFND3DKMT_RENDER Pfnd3dkmtRender; 

// Definition

NTSTATUS Pfnd3dkmtRender 
(
	D3DKMT_RENDER *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_RENDER](ns-d3dkmthk-_d3dkmt_render.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
