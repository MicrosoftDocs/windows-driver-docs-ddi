---
UID: NS:d3d12umddi.D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC
title: D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC (d3d12umddi.h)
description: Describes the Render Target. This is declared at the start of a Render Pass.
ms.assetid: 5dc9c92a-be5d-43a8-8da4-f195dd789f49
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC, D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC, 
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
req.typenames: D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC structure

## -description

Describes the Render Target. This is declared at the start of a Render Pass.

## -struct-fields

### -field cpuDescriptor

The [D3D12DDI_CPU_DESCRIPTOR_HANDLE](ns-d3d12umddi-d3d12ddi_cpu_descriptor_handle.md) structure that defines the Render Target.

### -field BeginningAccess

A [D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_0053.md) structure that specifies the Render Target, when a Render Pass is beginning.

### -field EndingAccess
 
A [D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_0053.md) structure that specifies the Render Target, when a Render Pass is ending.

## -remarks

## -see-also
