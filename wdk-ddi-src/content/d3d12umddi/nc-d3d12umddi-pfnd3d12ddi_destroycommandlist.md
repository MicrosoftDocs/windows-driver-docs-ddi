---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYCOMMANDLIST
title: PFND3D12DDI_DESTROYCOMMANDLIST
author: windows-driver-content
description: Destroys a command list.
ms.assetid: 275e31b7-359b-447d-90c7-7d69e6234645
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_DESTROYCOMMANDLIST
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_DESTROYCOMMANDLIST callback function

## -description

Destroys a command list.

## -prototype

```
//Declaration

PFND3D12DDI_DESTROYCOMMANDLIST Pfnd3d12ddiDestroycommandlist; 

// Definition

VOID Pfnd3d12ddiDestroycommandlist 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HCOMMANDLIST
)
{...}

PFND3D12DDI_DESTROYCOMMANDLIST 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HCOMMANDLIST: 

A command list handle.

## -returns

Returns VOID.

## -remarks




## -see-also