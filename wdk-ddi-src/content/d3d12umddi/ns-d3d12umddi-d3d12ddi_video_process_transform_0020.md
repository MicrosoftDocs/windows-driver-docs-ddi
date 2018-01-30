---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020
title: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020
author: windows-driver-content
description: Contains information for a transform.
old-location: display\d3d12ddi_video_process_transform.htm
old-project: display
ms.assetid: E463BD7F-F89C-4D82-ABCA-4AF48EC21655
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020, D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020, display.d3d12ddi_video_process_transform
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
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020
---

# D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020 structure


## -description


Contains information for a transform.


## -syntax


````
typedef struct D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020 {
  DXGI_RATIONAL                           SourceAspectRatio;
  DXGI_RATIONAL                           DestinationAspectRatio;
  D3D12DDI_RECT                           SourceRectangle;
  D3D12DDI_RECT                           DestinationRectangle;
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020 Orientation;
} D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020;
````


## -struct-fields




### -field SourceAspectRatio

The source aspect ratio.  


### -field DestinationAspectRatio

The destination aspect ratio.


### -field SourceRectangle

The source rectangle is the portion of the input surface that is bit block transferred to the destination surface. The source rectangle is given in pixel coordinates, relative to the input surface. Stereo format is implemented after orientation is applied.


### -field DestinationRectangle

The destination rectangle is the portion of the output surface that receives the bit block transfer for the stream. The destination rectangle is given in pixel coordinates relative to the output surface.


### -field Orientation

The rotation and flip operation to apply to the source.  Source and destination rectangles are specified in post orientation coordinates.

