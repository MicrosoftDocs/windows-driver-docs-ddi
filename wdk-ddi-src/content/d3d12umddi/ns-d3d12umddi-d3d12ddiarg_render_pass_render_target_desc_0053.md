---
UID: NS:d3d12umddi.D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053
title: D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053 (d3d12umddi.h)
description: Describes the Render Target. This is declared at the start of a Render Pass.
ms.assetid: e071cb29-be0b-4e26-b307-3e5e55dc0375
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053"
ms.keywords: D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053, D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053, 
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
req.typenames: D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053 structure

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
