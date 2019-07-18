---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032
title: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032 (d3d12umddi.h)
description: Command list functions for video decode.
old-location: display\d3d12ddi-command-list-funcs-video-decode-0032.htm
ms.assetid: 5e49e21c-57b8-4864-b4e5-a9baa8df129d
ms.date: 04/16/2018
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032, D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032 structure [Display Devices], d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032, display.d3d12ddi-command-list-funcs-video-decode-0032
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032
---

# D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032 structure


## -description


Command list functions for [D3D12DDI_TABLE_TYPE_COMMAND_LIST_VIDEO_DECODE](ne-d3d12umddi-d3d12ddi_table_type.md).


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


## -remarks

When [PFND3D12DDI_FILLDDITTABLE](nc-d3d12umddi-pfnd3d12ddi_fillddittable.md) is called for this table type, the *D3D12DDI_HRTTABLE* object must be stored to later call [PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB](nc-d3d12umddi-pfnd3d12ddi_setcommandlistdditable_cb.md) during command list creation.
