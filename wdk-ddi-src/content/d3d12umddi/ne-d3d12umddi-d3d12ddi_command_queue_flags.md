---
UID: NE:d3d12umddi.D3D12DDI_COMMAND_QUEUE_FLAGS
title: D3D12DDI_COMMAND_QUEUE_FLAGS (d3d12umddi.h)
description: Learn more about the D3D12DDI_COMMAND_QUEUE_FLAGS enumeration.
ms.date: 10/04/2024
keywords: ["D3D12DDI_COMMAND_QUEUE_FLAGS enumeration"]
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
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_COMMAND_QUEUE_FLAGS
f1_keywords:
 - D3D12DDI_COMMAND_QUEUE_FLAGS
 - d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_COMMAND_QUEUE_FLAGS
---

# D3D12DDI_COMMAND_QUEUE_FLAGS enumeration

## -description

The **D3D12DDI_COMMAND_QUEUE_FLAGS** enumeration specifies the type of command list to use on the command queue being created.

## -enum-fields

### -field D3D12DDI_COMMAND_QUEUE_FLAG_NONE:0x00000000

No flags are specified.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_3D:0x00000001

Indicates a command queue compatible with graphics pipelines.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE:0x00000002

Indicates a command queue compatible with compute pipelines.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_COPY:0x00000004

Indicates a command queue compatible with a copy engine.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_PAGING:0x00000008

Reserved; do not use.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_0020_VIDEO_LEGACY:0x00000010

Deprecated; do not use.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE:0x00000010

Indicates a command queue compatible with video decoding.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS:0x00000020

Indicates a command queue compatible with video processing.

### -field D3D12DDI_COMMAND_QUEUE_FLAG_0053_VIDEO_ENCODE:0x00000040

Indicates a command queue compatible with video encoding.

## -remarks

There are separate queue types for video decode and video processing. The video decode command queue only supports submitting video decode command lists and the video process command queue only supports submitting video process command lists. Both video decode and video process share the same DDI table definition, but separate table instances are retrieved from the driver for each type, see [**D3D12DDI_TABLE_TYPE**](ne-d3d12umddi-d3d12ddi_table_type.md).

Because video decode and video processing are separate queue types, they are necessarily separate queue instances. Applications are required to synchronize between separate queue instances; therefore, drivers must not implicitly synchronize between decode and video process queues.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_0089**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0089.md)

[**D3D12DDIARG_CREATECOMMANDQUEUE_0050**](ns-d3d12umddi-d3d12ddiarg_createcommandqueue_0050.md)

[**Pfnd3d12ddiCreatecommandqueue0050**](nc-d3d12umddi-pfnd3d12ddi_createcommandqueue_0050.md)
