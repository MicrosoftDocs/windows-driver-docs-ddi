---
UID: NE:d3d12umddi.D3D12DDI_3DPIPELINELEVEL
title: D3D12DDI_3DPIPELINELEVEL
author: windows-driver-content
description: Contains values that identify the pipeline level that the driver supports.
tech.root: display
ms.assetid: 39150f42-529e-4d79-bd70-10984a6783b0
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: enum
ms.keywords: D3D12DDI_3DPIPELINELEVEL, D3D12DDI_3DPIPELINELEVEL, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_3DPIPELINELEVEL
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_3DPIPELINELEVEL
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# D3D12DDI_3DPIPELINELEVEL enumeration

## -description

Contains values that identify the pipeline level that the driver supports. Drivers only report the maximum level they support.

## -enum-fields

### -field D3D12DDI_3DPIPELINELEVEL_1_0_CORE

Internal.

### -field D3D12DDI_3DPIPELINELEVEL_11_0

The driver supports Direct3D version 11 pipeline.

### -field D3D12DDI_3DPIPELINELEVEL_11_1

The driver supports Direct3D version 11.1 pipeline.

### -field D3D12DDI_3DPIPELINELEVEL_12_0

The driver supports Direct3D version 12.0 pipeline.

### -field D3D12DDI_3DPIPELINELEVEL_12_1 

The driver supports Direct3D version 12.1 pipeline.

## -remarks

## -see-also
