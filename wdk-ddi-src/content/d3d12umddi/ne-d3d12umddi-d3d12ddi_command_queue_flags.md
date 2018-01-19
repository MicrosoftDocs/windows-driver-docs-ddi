---
UID: NE:d3d12umddi.D3D12DDI_COMMAND_QUEUE_FLAGS
title: D3D12DDI_COMMAND_QUEUE_FLAGS
author: windows-driver-content
description: Contains values for the video command queue.
old-location: display\d3d12ddi_command_queue_flags.htm
old-project: display
ms.assetid: A5EFE133-6F63-4EA4-8F7F-B2B6A4E1838C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_COMMAND_QUEUE_FLAGS, D3D12DDI_COMMAND_QUEUE_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_COMMAND_QUEUE_FLAGS
req.alt-loc: D3d12umddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: D3D12DDI_COMMAND_QUEUE_FLAGS
---

# D3D12DDI_COMMAND_QUEUE_FLAGS enumeration



## -description
Contains values for the video command queue. 



## -syntax

````
typedef enum D3D12DDI_COMMAND_QUEUE_FLAGS { 
  D3D12DDI_COMMAND_QUEUE_FLAG_NONE                = 0x00000000,
  D3D12DDI_COMMAND_QUEUE_FLAG_3D                  = 0x00000001,
  D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE             = 0x00000002,
  D3D12DDI_COMMAND_QUEUE_FLAG_COPY                = 0x00000004,
  D3D12DDI_COMMAND_QUEUE_FLAG_PAGING              = 0x00000008,
  D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE   = 0x00000010,
  D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS  = 0x00000020
} D3D12DDI_COMMAND_QUEUE_FLAGS;
````


## -enum-fields

### -field D3D12DDI_COMMAND_QUEUE_FLAG_NONE

No flags.


### -field D3D12DDI_COMMAND_QUEUE_FLAG_3D

3D.


### -field D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE

Compute.


### -field D3D12DDI_COMMAND_QUEUE_FLAG_COPY

Copy.


### -field D3D12DDI_COMMAND_QUEUE_FLAG_PAGING

Paging.


### -field D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE

Decode video.


### -field D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS

Process video.


## -remarks
