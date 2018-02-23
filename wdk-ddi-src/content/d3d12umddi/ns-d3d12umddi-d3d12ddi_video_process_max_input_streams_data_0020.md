---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020
title: D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020
author: windows-driver-content
description: Specifies information used to retrieve the maximum number of input data streams that can be enabled for a video processor.
old-location: display\d3d12ddi_video_process_max_input_streams_data.htm
old-project: display
ms.assetid: 41518F04-4AD1-4057-8988-5934F3875B8E
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3d12umddi/D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020, D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020 structure [Display Devices], display.d3d12ddi_video_process_max_input_streams_data, D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020
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
-	D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020
---

# D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020 structure


## -description


Specifies information used to retrieve the maximum number of input data streams that can be enabled for a video processor.


## -syntax


````
typedef struct D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020 {
  UINT NodeIndex;
  UINT MaxInputStreams;
} D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020;
````


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field MaxInputStreams

The maximum number of streams that can be enabled for the video processor at the same time.

