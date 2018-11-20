---
UID: NS:d3d12umddi.D3D12DDI_LOCAL_ROOT_SIGNATURE_0054
title: D3D12DDI_LOCAL_ROOT_SIGNATURE_0054
author: windows-driver-content
description: Describes a local root signature.
ms.assetid: 90e65fc6-8bec-4144-a9a4-d517d7714eb2
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_LOCAL_ROOT_SIGNATURE_0054, D3D12DDI_LOCAL_ROOT_SIGNATURE_0054, 
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
req.typenames: D3D12DDI_LOCAL_ROOT_SIGNATURE_0054
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_LOCAL_ROOT_SIGNATURE_0054
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_LOCAL_ROOT_SIGNATURE_0054 structure

## -description

Describes a local root signature.

## -struct-fields

### -field hLocalRootSignature

A handle to the local root signature.

## -remarks

For ray tracing shaders, bindings can be defined by one or both of the following root signatures: 

* A local root signature, whose arguments come from shader tables, enabling each shader to have unique arguments.
* A root signature whose arguments are shared across all raytracing shaders and compute PSOs on CommandLists, set via [SetRootSignature](nc-d3d12umddi-pfnd3d12ddi_set_root_signature.md).  

Each ray tracing shader used together can use different local root signatures but must use the same root signature.

## -see-also
