---
UID: NC:d3d12umddi.PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050
title: PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050
author: windows-driver-content
description: Creates a virtual context associated with a scheduling group.
ms.assetid: 2f9548d8-0cde-42f4-9eee-ce1af049265b
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
-	PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050
product:
-	Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050 callback function

## -description

Creates a virtual context associated with a scheduling group. 

## -prototype

```
//Declaration

PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050 Pfnd3d12ddiCreateschedulinggroupcontextvirtualCb0050; 

// Definition

HRESULT Pfnd3d12ddiCreateschedulinggroupcontextvirtualCb0050 
(
	D3D12DDI_HRTSCHEDULINGGROUP_0050 hRTSchedulingGroup
	D3DDDICB_CREATECONTEXTVIRTUAL *
)
{...}

```

## -parameters

### -param hRTSchedulingGroup

A D3D12DDI_HRTSCHEDULINGGROUP_0050 runtime handle type that represents the contexts associated with a hardware scheduling group.

### -param *: 

A pointer to a [D3DDDICB_CREATECONTEXTVIRTUAL](..\d3dumddi\ns-d3dumddi-_d3dddicb_createcontextvirtual.md) structure that describes the context to create.

## -returns

Returns HRESULT.

## -remarks

This callback should be used with contexts that support virtual addressing.

## -see-also