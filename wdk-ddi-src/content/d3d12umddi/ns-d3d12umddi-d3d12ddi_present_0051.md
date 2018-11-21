---
UID: NS:d3d12umddi.D3D12DDI_PRESENT_0051
title: D3D12DDI_PRESENT_0051
author: windows-driver-content
description: Arguments that describe allocations that content is copied to and from.
ms.assetid: 517113ed-c43c-4041-9714-5c0d8e89d276
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_PRESENT_0051, D3D12DDI_PRESENT_0051, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_PRESENT_0051
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_PRESENT_0051
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_PRESENT_0051 structure

## -description

Arguments that describe allocations that content is copied to and from. Used by the [PFND3D12DDI_PRESENT_0051](nc-d3d12umddi-pfnd3d12ddi_present_0051.md) callback function.

## -struct-fields

### -field BroadcastSrcAllocation

Allocations which content will be presented.

### -field BroadcastDstAllocation

If non-zero, represents the destination allocations of the present.

### -field AddedGpuWork

Specifies whether there is added GPU work.

### -field BackBufferMultiplicity

The number of physical back buffer per logical back buffer.

### -field SyncIntervalOverrideValid

Override app sync interval is valid.

### -field SyncIntervalOverride
 
Override app sync interval.

## -remarks

## -see-also
