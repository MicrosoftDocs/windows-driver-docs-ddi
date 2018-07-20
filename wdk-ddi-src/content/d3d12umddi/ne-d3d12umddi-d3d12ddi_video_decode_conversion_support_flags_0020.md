---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020
title: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020
author: windows-driver-content
description: Contains flags for support of video decode conversion.
old-location: display\d3d12ddi_video_decode_conversion_support_flags.htm
tech.root: display
ms.assetid: 7E272786-ECD4-4DF0-A36A-B27454E3E896
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020, D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020 enumeration [Display Devices], D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAG_0020_NONE, D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAG_0020_SUPPORTED, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAG_0020_SUPPORTED, display.d3d12ddi_video_decode_conversion_support_flags
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
-	D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020
---

# D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020 enumeration


## -description


Contains flags for support of video decode conversion.


## -enum-fields




### -field D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAG_0020_NONE

No Flags set. The conversion is not supported.


### -field D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAG_0020_SUPPORTED

The conversion is supported. Callers must inspect the <b>ClosestWidth</b> and <b>ClosestHeight</b> members to understand scale support.

