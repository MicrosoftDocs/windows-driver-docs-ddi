---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032
title: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032
author: windows-driver-content
description: Video decode reference frames.
old-location: display\d3d12ddi-video-decode-reference-frames-0032.htm
old-project: display
ms.assetid: 58a814ab-629e-4528-a349-c469defc0a5a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032, D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032, display.d3d12ddi-video-decode-reference-frames-0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032
---

# D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032 structure


## -description


Video decode reference frames.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032 {
  D3D12DDI_HRESOURCE *               hDrvTexture2Ds;
  UINT *                             pSubresources;
  D3D12DDI_HVIDEODECODERHEAP_0032 *  hDrvVideoDecoderHeaps;
  UINT                               NumTexture2Ds;
} D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032, D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032;
````


## -struct-fields




### -field hDrvTexture2Ds

Texture.


### -field pSubresources

Subresources.


### -field hDrvVideoDecoderHeaps

Video decoder heaps.


### -field NumTexture2Ds

The number of textures.

