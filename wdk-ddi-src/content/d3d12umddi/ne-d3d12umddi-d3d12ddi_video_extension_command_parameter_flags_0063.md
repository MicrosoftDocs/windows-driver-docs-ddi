---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAGS_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAGS_0063
author: windows-driver-content
description: Video Extensions must specify a command parameter flag.
tech.root: display
ms.assetid: abdbd8ba-f534-416e-90ca-b2876774ba16
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: enum
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAGS_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAGS_0063, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAGS_0063
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAGS_0063
product:
- Windows
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAGS_0063 enumeration

## -description

Video Extensions must specify a command parameter flag.

## -enum-fields

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAG_0063_NONE

Set for print on demand (POD) parameters.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAG_0063_READ

Indicates that a GPU resource is read. Not valid for POD parameters.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAG_0063_WRITE

Indicates that a GPU resource is written. Not valid for POD parameters.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAG_0063_MASK 

Indicates read/write.

## -remarks

## -see-also
