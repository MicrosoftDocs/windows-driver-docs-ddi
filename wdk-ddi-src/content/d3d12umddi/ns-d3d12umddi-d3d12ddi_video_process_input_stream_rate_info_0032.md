---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
author: windows-driver-content
description: The video process input stream rate info.
old-location: display\d3d12ddi-video-process-input-stream-rate-info-0032.htm
old-project: display
ms.assetid: 4ca68dac-ead1-431e-a97e-af99ef966417
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 structure [Display Devices], E, F, I, M, N, O, P, R, S, T, U, V, _, d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032, display.d3d12ddi-video-process-input-stream-rate-info-0032"
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
-	D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 structure


## -description


The video process input stream rate info.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 {
  UINT  OutputIndex;
  UINT  InputFrameOrField;
} D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032;
````


## -struct-fields




### -field OutputIndex

The output index.


### -field InputFrameOrField

The input frame or field.

