---
UID: NE:d3d12umddi.D3D12DDI_HANDLETYPE
title: D3D12DDI_HANDLETYPE (d3d12umddi.h)
description: Contains driver handle types.
old-location: display\d3d12ddi_handletype.htm
ms.date: 05/24/2022
keywords: ["D3D12DDI_HANDLETYPE enumeration"]
ms.keywords: D3D12DDI_HANDLETYPE, D3D12DDI_HANDLETYPE enumeration [Display Devices], D3D12DDI_HT_0010_PIPELINE_LIBRARY, D3D12DDI_HT_0012_RESOURCE, D3D12DDI_HT_0020_VIDEO_DECODER, D3D12DDI_HT_0020_VIDEO_DECODE_STREAM, D3D12DDI_HT_0020_VIDEO_PROCESSOR, D3D12DDI_HT_0020_VIDEO_PROCESS_STREAM, D3D12DDI_HT_0030_CRYPTOSESSION, D3D12DDI_HT_0030_CRYPTOSESSIONPOLICY, D3D12DDI_HT_0030_PROTECTEDRESOURCESESSION, D3D12DDI_HT_0032_VIDEO_DECODER_HEAP, D3D12DDI_HT_COMMAND_ALLOCATOR, D3D12DDI_HT_COMMAND_LIST, D3D12DDI_HT_COMMAND_QUEUE, D3D12DDI_HT_COMMAND_SIGNATURE, D3D12DDI_HT_DESCRIPTOR_HEAP, D3D12DDI_HT_FENCE, D3D12DDI_HT_HEAP, D3D12DDI_HT_PASS, D3D12DDI_HT_PIPELINE_STATE, D3D12DDI_HT_QUERY_HEAP, d3d12umddi/D3D12DDI_HANDLETYPE, d3d12umddi/D3D12DDI_HT_0010_PIPELINE_LIBRARY, d3d12umddi/D3D12DDI_HT_0012_RESOURCE, d3d12umddi/D3D12DDI_HT_0020_VIDEO_DECODER, d3d12umddi/D3D12DDI_HT_0020_VIDEO_DECODE_STREAM, d3d12umddi/D3D12DDI_HT_0020_VIDEO_PROCESSOR, d3d12umddi/D3D12DDI_HT_0020_VIDEO_PROCESS_STREAM, d3d12umddi/D3D12DDI_HT_0030_CRYPTOSESSION, d3d12umddi/D3D12DDI_HT_0030_CRYPTOSESSIONPOLICY, d3d12umddi/D3D12DDI_HT_0030_PROTECTEDRESOURCESESSION, d3d12umddi/D3D12DDI_HT_0032_VIDEO_DECODER_HEAP, d3d12umddi/D3D12DDI_HT_COMMAND_ALLOCATOR, d3d12umddi/D3D12DDI_HT_COMMAND_LIST, d3d12umddi/D3D12DDI_HT_COMMAND_QUEUE, d3d12umddi/D3D12DDI_HT_COMMAND_SIGNATURE, d3d12umddi/D3D12DDI_HT_DESCRIPTOR_HEAP, d3d12umddi/D3D12DDI_HT_FENCE, d3d12umddi/D3D12DDI_HT_HEAP, d3d12umddi/D3D12DDI_HT_PASS, d3d12umddi/D3D12DDI_HT_PIPELINE_STATE, d3d12umddi/D3D12DDI_HT_QUERY_HEAP, display.d3d12ddi_handletype
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
req.typenames: D3D12DDI_HANDLETYPE
ms.custom: 19H1
f1_keywords:
 - D3D12DDI_HANDLETYPE
 - d3d12umddi/D3D12DDI_HANDLETYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_HANDLETYPE
dev_langs:
 - c++
---

# D3D12DDI_HANDLETYPE enumeration

## -description

A **D3D12DDI_HANDLETYPE** value identifies a driver handle type.

## -enum-fields

### -field D3D12DDI_HT_COMMAND_QUEUE:19

A command queue handle type.

### -field D3D12DDI_HT_COMMAND_ALLOCATOR:20

A command allocator handle type.

### -field D3D12DDI_HT_PIPELINE_STATE:21

A pipeline state handle type.

### -field D3D12DDI_HT_COMMAND_LIST:22

A command list handle type.

### -field D3D12DDI_HT_FENCE:23

A fence handle type.

### -field D3D12DDI_HT_DESCRIPTOR_HEAP:24

A descriptor heap handle type.

### -field D3D12DDI_HT_HEAP:25

A heap handle type.

### -field D3D12DDI_HT_QUERY_HEAP:27

A query heap handle type.

### -field D3D12DDI_HT_COMMAND_SIGNATURE:28

A command signature handle type.

### -field D3D12DDI_HT_0010_PIPELINE_LIBRARY:29

A pipeline library handle type.

### -field D3D12DDI_HT_0020_VIDEO_DECODER:30

A video decoder handle type.

### -field D3D12DDI_HT_0020_VIDEO_PROCESSOR:32

A video processor handle type.

### -field D3D12DDI_HT_0012_RESOURCE:34

A resource handle type.

### -field D3D12DDI_HT_PASS:35

A pass handle type.

### -field D3D12DDI_HT_0030_CRYPTOSESSION:36

A crypto session handle type.

### -field D3D12DDI_HT_0030_CRYPTOSESSIONPOLICY:37

A crypto session policy handle type.

### -field D3D12DDI_HT_0030_PROTECTEDRESOURCESESSION:38

A protected resource session handle type.

### -field D3D12DDI_HT_0032_VIDEO_DECODER_HEAP:39

A video decoder heap handle type.

### -field D3D12DDI_HT_0040_COMMAND_POOL:40

A command pool.

### -field D3D12DDI_HT_0040_COMMAND_RECORDER:41

A command recorder.

### -field D3D12DDI_HT_0054_STATE_OBJECT:42

A state object.

### -field D3D12DDI_HT_METACOMMAND:43

A meta-command.

### -field D3D12DDI_HT_0050_SCHEDULINGGROUP:44

Hardware scheduling group.

### -field D3D12DDI_HT_0053_VIDEO_MOTION_ESTIMATOR:45

Video motion estimator.

### -field D3D12DDI_HT_0053_VIDEO_MOTION_VECTOR_HEAP:46

Video motion vector heap.

### -field D3D12DDI_HT_0061_VIDEO_EXTENSION_COMMAND:47

The handle type for Video Extension Commands. Used in DDI such as pfnMakeResident and pfnEvict that can accept multiple handle types.

The UMD handle type declaration is `D3D12DDI_HVIDEOEXTENSIONCOMMAND_0063`.

This field is available starting in Windows 10, version 1903 and UMD DDI Min Version D3D12DDI_SUPPORTED_0043.

### -field D3D12DDI_HT_0080_VIDEO_ENCODER:48

Handle type for a video encoder.

### -field D3D12DDI_HT_0080_VIDEO_ENCODER_HEAP:49

Handle type for a video encoder heap.
