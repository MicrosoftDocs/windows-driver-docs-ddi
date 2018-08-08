---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020
title: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020
author: windows-driver-content
description: Contains the reference frames for the current decode operation.
old-location: display\d3d12ddi_video_decode_reference_frames.htm
tech.root: display
ms.assetid: B7ED4ADA-572A-4D15-B8FD-6EAF2DB87157
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020, D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020, display.d3d12ddi_video_decode_reference_frames
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
-	D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020
---

# D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020 structure


## -description


Contains the reference frames for the current decode operation.


## -struct-fields




### -field hDrvTexture2Ds




### -field pSubresources




### -field NumTexture2Ds






#### - NumReferenceResources

The number of references specified.


#### - hDrvReferenceTexture2Ds

The reference textures.


#### - pReferenceSubresources

An array of subresource indexes for the list of reference textures.  A value of null indicates to assume a subresource of zero (0) for each resource.


## -remarks



Either a Texture Array or an array of textures can be specified.

Specifies the reference frames for the current decode operation.  Decode profiles that report <b>D3D12DDI_VIDEO_DECODE_TIER_1</b> or <b>D3D12DDI_VIDEO_DECODE_TIER_2</b> require the use of a texture array, so the list of <b>ppReferenceTexture2Ds</b> is always the same texture and <b>pReferenceSubresources</b> is used to index into the texture array.  For <b>D3D12DDI_VIDEO_DECODE_TIER_3</b>, either a Texture Array or an array of textures can be specified.



