---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
title: D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
author: windows-driver-content
description: Contains values for alpha fill modes.
old-location: display\d3d12ddi_video_process_alpha_fill_mode.htm
old-project: display
ms.assetid: 74F07876-5502-4B57-9128-624F6066AF5B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020, D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020 enumeration [Display Devices], D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_BACKGROUND, D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_DESTINATION, D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_OPAQUE, D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_SOURCE_STREAM, d3d12umddi/D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020, d3d12umddi/D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_BACKGROUND, d3d12umddi/D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_DESTINATION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_OPAQUE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_SOURCE_STREAM, display.d3d12ddi_video_process_alpha_fill_mode
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
-	D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
---

# D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020 enumeration


## -description


Contains values for alpha fill modes.


## -syntax


````
typedef enum D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020 { 
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_OPAQUE         = 0,
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_BACKGROUND     = 1,
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_DESTINATION    = 2,
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_SOURCE_STREAM  = 3
} D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020;
````


## -enum-fields




### -field D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_OPAQUE

Alpha values inside the target rectangle are set to opaque. 


### -field D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_BACKGROUND

Alpha values inside the target rectangle are set to the alpha value specified in the background color. 


### -field D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_DESTINATION

Existing alpha values remain unchanged in the output surface.


### -field D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_SOURCE_STREAM

Alpha values are taken from an input stream, scaled, and copied to the corresponding destination rectangle for that stream. The input stream is specified in the <b>AlphaFillModeSourceStreamIndex</b> member of the <b>D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_PARAMETERS</b> structure. If the input stream does not have alpha data, the video processor sets the alpha values in the target rectangle to opaque. If the input stream is disabled or the source rectangle is empty, the alpha values in the target rectangle are not modified.



## -remarks



The alpha fill mode is used in <b>D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_PARAMETERS</b>.  The <b>D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_OPAQUE</b> flag is always supported.  The background, destination, and source stream modes are only supported when the driver reports <b>D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAG_ALPHA_FILL</b>.



