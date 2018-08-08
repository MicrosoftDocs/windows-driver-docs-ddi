---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
title: D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
author: windows-driver-content
description: Contains the compressed bitstream from which to decode.
old-location: display\d3d12ddi_video_decode_compressed_bitstream.htm
tech.root: display
ms.assetid: 24A1D8C7-E432-45CB-8DEA-C1137159E319
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020, D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020, display.d3d12ddi_video_decode_compressed_bitstream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.max-support: Windows 10, version 1709
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
-	D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
---

# D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020 structure


## -description


Contains the compressed bitstream from which  to decode.


## -struct-fields




### -field hDrvBuffer

The source buffer that contains the compressed bitstream to decode.


### -field Offset

The offset to the beginning of the first slice.  This offset has alignment requirements based on the tier value.

