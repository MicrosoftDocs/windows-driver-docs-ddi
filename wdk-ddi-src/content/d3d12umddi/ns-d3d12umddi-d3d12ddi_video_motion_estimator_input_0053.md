---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053
title: D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053 (d3d12umddi.h)
description: Describes the input to the motion estimation operation.
ms.assetid: 8c2cee49-aaa9-4a86-9eb9-d78ce3e6b738
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053, D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053 structure

## -description

Describes the input to the motion estimation operation.

## -struct-fields

### -field hDrvInputTexture2D

The handle of the current frame.

### -field InputSubresourceIndex

Specifies the start coordinates of the motion estimation operation for hDrvInputTexture2D.

### -field hDrvReferenceTexture2D

The handle of the reference frame, or Past frame, used for motion estimation.

### -field ReferenceSubresourceIndex

A 256-byte aligned offset into the hDrvPreviousMotionVectorHeap buffer indicating the start of the hardware dependent data.

### -field hDrvPreviousMotionVectorHeap
 
This parameter may be NULL, indicating that the previous motion estimator output should not be considered for this operation. If non-NULL, this buffer contains the hardware dependent output of the previous motion estimator operation and may be used for hinting the current operation.

## -remarks

## -see-also
