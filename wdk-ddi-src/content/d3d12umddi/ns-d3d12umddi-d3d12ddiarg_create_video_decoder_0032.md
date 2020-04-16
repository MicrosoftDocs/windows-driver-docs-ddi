---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_DECODER_0032
title: D3D12DDIARG_CREATE_VIDEO_DECODER_0032 (d3d12umddi.h)
description: Creates a video decoder.
old-location: display\d3d12ddiarg-create-video-decoder-0032.htm
ms.assetid: d4d42334-ae09-4900-828b-86da81b446c1
ms.date: 04/16/2018
keywords: ["D3D12DDIARG_CREATE_VIDEO_DECODER_0032 structure"]
ms.keywords: D3D12DDIARG_CREATE_VIDEO_DECODER_0032, D3D12DDIARG_CREATE_VIDEO_DECODER_0032 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_0032, display.d3d12ddiarg-create-video-decoder-0032
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_0032"
req.header: d3d12umddi.h
req.include-header:
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDIARG_CREATE_VIDEO_DECODER_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_CREATE_VIDEO_DECODER_0032
---

# D3D12DDIARG_CREATE_VIDEO_DECODER_0032 structure


## -description


Used to create a decoder object for a decode session. The decoder holds state for a decode session, but references any significant allocations from the video decoder heap.


## -struct-fields




### -field NodeMask

Represents the set of nodes. For a single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.


### -field Configuration

The decode profile and bitstream encryption. See [D3D12DDI_VIDEO_DECODE_CONFIGURATION](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md).

