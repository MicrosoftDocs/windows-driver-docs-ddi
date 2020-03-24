---
UID: NE:d3d12umddi.D3D12DDIARG_RENDER_PASS_FLAGS_0053
title: D3D12DDIARG_RENDER_PASS_FLAGS_0053 (d3d12umddi.h)
description: Indicates the state of the Render Pass.
ms.assetid: 1ff42584-e2d3-4f47-8dac-3262fc375491
ms.date: 10/19/2018
keywords: ["D3D12DDIARG_RENDER_PASS_FLAGS_0053 enumeration"]
ms.keywords: D3D12DDIARG_RENDER_PASS_FLAGS_0053, D3D12DDIARG_RENDER_PASS_FLAGS_0053,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDIARG_RENDER_PASS_FLAGS_0053
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_RENDER_PASS_FLAGS_0053"
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_RENDER_PASS_FLAGS_0053
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDIARG_RENDER_PASS_FLAGS_0053 enumeration

## -description

Indicates the state of the Render Pass.

## -enum-fields

### -field D3D12DDI_RENDER_PASS_FLAG_0053_NONE

No flags are specified.

### -field D3D12DDI_RENDER_PASS_FLAG_0053_ALLOW_UAV_WRITES

Used to specify whether the user will be issuing UAV writes within the Render Pass, allowing UMDs (user mode drivers) to opt out of tiling if necessary.

### -field D3D12DDI_RENDER_PASS_FLAG_0053_SUSPENDING_PASS

The Render Pass is suspending.

### -field D3D12DDI_RENDER_PASS_FLAG_0053_RESUMING_PASS

The Render Pass is resuming.

## -remarks

A render pass can be both resuming and suspending.

## -see-also

