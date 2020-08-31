---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1
title: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1 (d3d12umddi.h)
description: Command list functions for video decode.
ms.assetid: b16541f4-4844-4cbc-b904-2424d13e6880
ms.date: 10/19/2018
keywords: ["D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1 structure"]
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1, D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1
targetos: Windows
tech.root: display
f1_keywords:
 - D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1
 - d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1
product:
 - Windows
---

# D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1 structure


## -description

Command list functions for video decode.

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

### -field pfnDecodeFrame

Decode frame.

### -field pfnSetProtectedResourceSession

Set protected resource session.

### -field pfnWriteBufferImmediate

Write buffer immediate.

## -syntax

```cpp
typedef struct D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1
{
    PFND3D12DDI_CLOSECOMMANDLIST                            pfnCloseCommandList;
    PFND3D12DDI_RESETCOMMANDLIST_0040                       pfnResetCommandList;
    PFND3D12DDI_DISCARD_RESOURCE_0003                       pfnDiscardResource;
    PFND3D12DDI_SET_MARKER                                  pfnSetMarker;
    PFND3D12DDI_SET_PREDICATION                             pfnSetPredication;
    PFND3D12DDI_BEGIN_END_QUERY_0003                        pfnBeginQuery;
    PFND3D12DDI_BEGIN_END_QUERY_0003                        pfnEndQuery;
    PFND3D12DDI_RESOLVE_QUERY_DATA                          pfnResolveQueryData;
    PFND3D12DDI_RESOURCEBARRIER_0022                        pfnResourceBarrier;
    PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1                   pfnDecodeFrame;
    PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030            pfnSetProtectedResourceSession;
    PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032                   pfnWriteBufferImmediate;
} D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0041_1;
```

