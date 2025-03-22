---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088
tech.root: display
title: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088 structure.
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
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088
f1_keywords:
 - D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088
 - d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088
---

# D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088 structure (d3d12umddi.h)

## -description

The **D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088** structure contains pointers to command list functions for video decode, version D3D12DDI_FEATURE_VERSION_VIDEO_0088.

## -struct-fields

### -field pfnCloseCommandList

Pointer to a **PFND3D12DDI_CLOSECOMMANDLIST** function that closes the command list.

### -field pfnResetCommandList

Pointer to a [**PFND3D12DDI_RESETCOMMANDLIST_0040**](nc-d3d12umddi-pfnd3d12ddi_resetcommandlist_0040.md) function that resets the command list.

### -field pfnDiscardResource

Pointer to a **PFND3D12DDI_DISCARD_RESOURCE_0003** function that discards a resource.

### -field pfnSetMarker

Pointer to a **PFND3D12DDI_SET_MARKER** function that sets a marker.

### -field pfnSetPredication

Pointer to a **PFND3D12DDI_SET_PREDICATION** function that sets predication.

### -field pfnBeginQuery

Pointer to a **PFND3D12DDI_BEGIN_END_QUERY_0003** function that begins a query.

### -field pfnEndQuery

Pointer to a **PFND3D12DDI_BEGIN_END_QUERY_0003** function that ends a query.

### -field pfnResolveQueryData

Pointer to a **PFND3D12DDI_RESOLVE_QUERY_DATA** function that resolves query data.

### -field pfnResourceBarrier

Pointer to a **PFND3D12DDI_RESOURCEBARRIER_0022** function.

### -field pfnDecodeFrame

Pointer to a **PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1** function.

### -field pfnSetProtectedResourceSession

Pointer to a **PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030** function.

### -field pfnWriteBufferImmediate

Pointer to a **PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032** function.

### -field pfnInitializeVideoExtensionCommand

Pointer to a **PFND3D12DDI_INITIALIZE_VIDEO_EXTENSION_COMMAND_0063** function.

### -field pfnExecuteVideoExtensionCommand

Pointer to **PFND3D12DDI_EXECUTE_VIDEO_EXTENSION_COMMAND_0063** function.

### -field pfnBarrier

Pointer to a **PFND3D12DDI_BARRIER_0088** function.

## -remarks

## -see-also

