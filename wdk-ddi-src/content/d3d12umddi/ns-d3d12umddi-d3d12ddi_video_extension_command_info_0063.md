---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063
author: windows-driver-content
description: Describes an extension.
tech.root: display
ms.assetid: 46a4af86-19e7-4c93-a642-57ce51cd7d5a
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063"
 - "D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063"
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_INFO_0063 structure

## -description

Describes an extension.

## -struct-fields

### -field CommandId

The unique identifier for the video extension command.

### -field Name

Pointer to a wide string, driver allocates and keep for the lifetime of the device.

### -field CommandQueueFlags

Indicates the Video Command Queue that the video extension targets. Only one of the following bits may be set:

* D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE
* D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS
* D3D12DDI_COMMAND_QUEUE_FLAG_0053_VIDEO_ENCODE


## -remarks

## -see-also
