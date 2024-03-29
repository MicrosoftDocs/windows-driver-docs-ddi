---
UID: NC:d3d12umddi.PFND3D12DDI_RESETCOMMANDLIST_0040
title: PFND3D12DDI_RESETCOMMANDLIST_0040 (d3d12umddi.h)
description: Implemented by the client driver to reset a command list back to its initial state as if a new command list was just created.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_RESETCOMMANDLIST_0040 callback function"]
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
targetos: Windows
tech.root: display
f1_keywords:
 - PFND3D12DDI_RESETCOMMANDLIST_0040
 - d3d12umddi/PFND3D12DDI_RESETCOMMANDLIST_0040
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_RESETCOMMANDLIST_0040
---

# PFND3D12DDI_RESETCOMMANDLIST_0040 callback function


## -description

Implemented by the client driver to reset a command list back to its initial state as if a new command list was just created.

## -parameters

### -param unnamedParam1

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param unnamedParam2

A pointer to the D3D12DDIARG_RESETCOMMANDLIST_0040 structure that contains arguments to reset the command list.

## -prototype

```cpp
//Declaration

PFND3D12DDI_RESETCOMMANDLIST_0040 Pfnd3d12ddiResetcommandlist0040;

// Definition

VOID Pfnd3d12ddiResetcommandlist0040
(
	 D3D12DDI_HCOMMANDLIST
	CONST D3D12DDIARG_RESETCOMMANDLIST_0040 *
)
{...}

PFND3D12DDI_RESETCOMMANDLIST_0040


```

## -see-also

