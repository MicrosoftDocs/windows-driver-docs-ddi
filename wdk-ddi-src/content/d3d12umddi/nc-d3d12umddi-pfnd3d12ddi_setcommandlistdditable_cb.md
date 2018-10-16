---
UID: NC:d3d12umddi.PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB
title: PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB
author: windows-driver-content
description: Sets the command list table.
ms.assetid: d1480f13-37d6-465c-b468-bf7a32bf0523
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
-	PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB callback function

## -description

Sets the command list table.

## -prototype

```cpp
//Declaration

PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB Pfnd3d12ddiSetcommandlistdditableCb;

// Definition

VOID Pfnd3d12ddiSetcommandlistdditableCb
(
	 D3D12DDI_HRTCOMMANDLIST
	 D3D12DDI_HRTTABLE
)
{...}

PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB


```

## -parameters

### -param D3D12DDI_HRTCOMMANDLIST

A handle to a command list.

### -param D3D12DDI_HRTTABLE:

A handle to a table.

## -returns

Returns VOID.

