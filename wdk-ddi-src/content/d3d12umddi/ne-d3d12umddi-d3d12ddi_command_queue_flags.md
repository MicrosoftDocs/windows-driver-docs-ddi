---
UID: NE:d3d12umddi.D3D12DDI_COMMAND_QUEUE_FLAGS
title: D3D12DDI_COMMAND_QUEUE_FLAGS
author: windows-driver-content
description: Contains values for the video command queue.
old-location: display\d3d12ddi_command_queue_flags.htm
ms.assetid: A5EFE133-6F63-4EA4-8F7F-B2B6A4E1838C
ms.date: 04/16/2018
ms.keywords: D3D12DDI_COMMAND_QUEUE_FLAGS, D3D12DDI_COMMAND_QUEUE_FLAGS enumeration [Display Devices], D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE, D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS, D3D12DDI_COMMAND_QUEUE_FLAG_3D, D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE, D3D12DDI_COMMAND_QUEUE_FLAG_COPY, D3D12DDI_COMMAND_QUEUE_FLAG_NONE, D3D12DDI_COMMAND_QUEUE_FLAG_PAGING, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAGS, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_3D, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_COPY, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_NONE, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_PAGING, display.d3d12ddi_command_queue_flags
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_COMMAND_QUEUE_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_COMMAND_QUEUE_FLAGS
---

# D3D12DDI_COMMAND_QUEUE_FLAGS enumeration


## -description


Contains values for the video command queue.


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


### -field D3D12DDI_COMMAND_QUEUE_FLAG_0020_VIDEO_LEGACY


### -field D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE

Decode video.


### -field D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS

Process video.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_0053_VIDEO_ENCODE

Video encode.

## -remarks

There are separate queue types for video decode and video processing.  The video decode command queue only supports submitting video decode command lists and the video process command queue only supports submitting video process command lists.  Both video decode and video process share the same DDI table definition, but separate table instances are retrieved from the driver for each type, see [D3D12DDI_TABLE_TYPE](ne-d3d12umddi-d3d12ddi_table_type.md).

Because video decode and video processing are separate queue types, they are necessarily separate queue instances.  Applications are required to synchronize between separate queue instances; therefore, drivers must not implicitly synchronize between decode and video process queues.
