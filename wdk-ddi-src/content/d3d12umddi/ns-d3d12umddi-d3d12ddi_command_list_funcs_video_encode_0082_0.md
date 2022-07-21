---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0082_0
tech.root: display
title: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0082_0 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0082_0
f1_keywords:
 - D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0082_0
 - d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0082_0** structure contains the command list functions for video encoding, version D3D12DDI_FEATURE_VERSION_VIDEO_0082_0.

## -struct-fields

### -field pfnCloseCommandList

Close command list.

### -field pfnResetCommandList

Reset command list.

### -field pfnDiscardResource

Discard resource.

### -field pfnSetMarker

Set marker.

### -field pfnSetPredication

Set predication.

### -field pfnBeginQuery

Begin query.

### -field pfnEndQuery

End query.

### -field pfnResolveQueryData

Resolve query data.

### -field pfnResourceBarrier

Resource barrier.

### -field pfnEstimateMotion

Decode frame.

### -field pfnSetProtectedResourceSession

Set protected resource session.

### -field pfnWriteBufferImmediate

Write buffer immediate.

### -field pfnResolveVideoMotionVectorHeap

 
Resolve video motion vector heap.

### -field pfnInitializeVideoExtensionCommand

Records a command to initialize or re-initialize a Video Extension Command into a command list.

### -field pfnExecuteVideoExtensionCommand

Records a command to execute a video extension command into a command list.

### -field pfnResolveEncoderOutputMetadata

Resolves an video encoder's output metadata.

### -field pfnEncodeFrame

Video encodes a frame.

## -remarks

## -see-also
