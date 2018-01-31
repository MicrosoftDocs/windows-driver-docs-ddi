---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030
title: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030
author: windows-driver-content
description: Command list functions for video process.
old-location: display\d3d12ddi-command-list-funcs-video-process-0030.htm
old-project: display
ms.assetid: b45b79bd-90d6-4bc5-b56a-99d2b71e216a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030 structure [Display Devices], D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030, display.d3d12ddi-command-list-funcs-video-process-0030, d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030
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
-	D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030
---

# D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030 structure


## -description


Command list functions for video process.


## -syntax


````
typedef struct _D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030 {
  PFND3D12DDI_CLOSECOMMANDLIST                  pfnCloseCommandList;
  PFND3D12DDI_RESETCOMMANDLIST                  pfnResetCommandList;
  PFND3D12DDI_DISCARD_RESOURCE_0003             pfnDiscardResource;
  PFND3D12DDI_SET_MARKER                        pfnSetMarker;
  PFND3D12DDI_SET_PREDICATION                   pfnSetPredication;
  PFND3D12DDI_BEGIN_END_QUERY_0003              pfnBeginQuery;
  PFND3D12DDI_BEGIN_END_QUERY_0003              pfnEndQuery;
  PFND3D12DDI_RESOLVE_QUERY_DATA                pfnResolveQueryData;
  PFND3D12DDI_RESOURCEBARRIER_0022              pfnResourceBarrier;
  PFND3D12DDI_VIDEO_PROCESS_FRAME_0021          pfnProcessFrame;
  PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030  pfnSetProtectedResourceSession;
} D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030, D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030;
````


## -struct-fields




#### - pfnCloseCommandList

Close command list.


#### - pfnResetCommandList

Reset command list.


#### - pfnDiscardResource

Discard resource.


#### - pfnSetMarker

Set marker.


#### - pfnSetPredication

Set predication.


#### - pfnBeginQuery

Begin query.


#### - pfnEndQuery

End query.


#### - pfnResolveQueryData

Resolve query data.


#### - pfnResourceBarrier

Resource barrier.


#### - pfnProcessFrame

Process frame.


#### - pfnSetProtectedResourceSession

Set protected resource session.

