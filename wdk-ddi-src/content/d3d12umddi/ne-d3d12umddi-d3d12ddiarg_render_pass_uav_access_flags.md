---
UID: NE:d3d12umddi.D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS
title: D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS
author: windows-driver-content
description: Used to specify what type of UAV access to perform within the Render Pass.
ms.assetid: 818b0fec-d52b-419f-b14e-86db6fc07e1a
ms.date: 
ms.topic: enum
ms.keywords: D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS, D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS enumeration

## -description

Used to specify what type of UAV (Unordered Access View) access to perform within the Render Pass.

## -enum-fields

### -field D3D12DDI_RENDER_PASS_UAV_ACCESS_NO_ACCESS

Indicates that the Render Pass does not allow UAV access.

### -field D3D12DDI_RENDER_PASS_UAV_ACCESS_READ

Indicates that the Render Pass allows read access.

### -field D3D12DDI_RENDER_PASS_UAV_ACCESS_WRITE

Indicates that the Render Pass allows write access.

## -remarks

UAV bindings via root tables or root descriptors are inherited into Render Passes, and are propagated out of Render Passes.

## -see-also
