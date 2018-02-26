---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODER_TRIM_ALLOCATIONS_0021
title: PFND3D12DDI_VIDEO_DECODER_TRIM_ALLOCATIONS_0021
author: windows-driver-content
description: The pfnDecoderTrimAllocations callback function trims allocations for submissions that are finished.
old-location: display\pfnd3d12ddi_video_decoder_trim_allocations.htm
old-project: display
ms.assetid: 2E90B365-8C5D-4586-AAA8-D49CC9BBCF70
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D12DDI_VIDEO_DECODER_TRIM_ALLOCATIONS_0021, d3d12umddi/pfnDecoderTrimAllocations, display.pfnd3d12ddi_video_decoder_trim_allocations, pfnDecoderTrimAllocations, pfnDecoderTrimAllocations callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnDecoderTrimAllocations
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_DECODER_TRIM_ALLOCATIONS_0021 callback


## -description


The <i>pfnDecoderTrimAllocations</i> callback function trims allocations for submissions that are finished.


## -prototype


````
PFND3D12DDI_VIDEO_DECODER_TRIM_ALLOCATIONS_0021 pfnDecoderTrimAllocations;

UINT64 APIENTRY* pfnDecoderTrimAllocations(
   D3D12DDI_HVIDEODECODETREAM hDrvVideoDecoder,
   UINT64                     SubmissionID
)
{ ... }
````


## -parameters




### -param hdrvDevice


### -param hDrvVideoDecoder

The video decoder for which to submit this frame.


### -param SubmissionID

The submission ID is a monotonically increasing integer value.  The value passed to this method indicates that the submission ID and all earlier values are now complete and the driver may free or re-use resources associated with this ID.


## -remarks



Applications track command completion.  To allow driver to manage memory, an application calls this method with a <i>SubmissionID</i> parameter to indicate which submissions are complete.



