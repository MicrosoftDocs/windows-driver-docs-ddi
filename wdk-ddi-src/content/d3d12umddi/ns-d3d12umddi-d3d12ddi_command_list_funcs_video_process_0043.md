---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043
title: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043
author: windows-driver-content
description: The command list functions for video processing.
ms.assetid: 8a0bc132-117d-47cf-8d7b-bd16d2280304
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043, D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043,
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
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043 structure

## -description

The command list functions for video processing.


## -syntax


````
typedef struct D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043
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
    PFND3D12DDI_VIDEO_PROCESS_FRAME_0043                    pfnProcessFrame;
    PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030            pfnSetProtectedResourceSession;
    PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032                   pfnWriteBufferImmediate;
} D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0043;
````

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


### -field pfnProcessFrame

Decode frame.


### -field pfnSetProtectedResourceSession

Set protected resource session.


### -field pfnWriteBufferImmediate

Write buffer immediate.

