---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021
title: PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021 (d3d12umddi.h)
description: The pfnProcessorTrimAllocations callback function trims allocations for submissions that are finished.
old-location: display\pfnd3d12ddi_video_processor_trim_allocations.htm
ms.assetid: 505B3502-FC2D-47FB-B8CD-3D7DE9ED4770
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021 callback function"]
ms.keywords: PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021, PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021 callback, d3d12umddi/pfnProcessorTrimAllocations, display.pfnd3d12ddi_video_processor_trim_allocations, pfnProcessorTrimAllocations, pfnProcessorTrimAllocations callback function [Display Devices]
f1_keywords:
 - "d3d12umddi/pfnProcessorTrimAllocations"
 - "pfnProcessorTrimAllocations"
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
req.max-support: Windows 10, version 1709
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
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- pfnProcessorTrimAllocations
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021 callback function


## -description


The <i>pfnProcessorTrimAllocations</i> callback function  trims allocations for submissions that are finished.


## -parameters




### -param hdrvDevice


### -param hDrvVideoProcessor

The video processor for which to submit this frame.


### -param SubmissionID

The submission ID is a monotonically increasing integer value.  The value passed to this method indicates that the submission ID and all earlier values are now complete and the driver may free or re-use resources associated with this ID.


## -remarks



Applications track command completion.  To allow driver to manage memory, an application calls this method with a <i>SubmissionID</i> parameter to indicate which submissions are complete.



