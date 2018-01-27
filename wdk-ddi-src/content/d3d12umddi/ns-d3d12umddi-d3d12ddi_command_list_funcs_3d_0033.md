---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_3D_0033
title: D3D12DDI_COMMAND_LIST_FUNCS_3D_0033
author: windows-driver-content
description: The command list functions for 3D.
old-location: display\d3d12ddi-command-list-funcs-3d-0033.htm
old-project: display
ms.assetid: 421e0623-0679-4068-b8e0-f0278abd2caf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_3D_0033, d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_3D_0033, D3D12DDI_COMMAND_LIST_FUNCS_3D_0033 structure [Display Devices], display.d3d12ddi-command-list-funcs-3d-0033
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
-	D3D12DDI_COMMAND_LIST_FUNCS_3D_0033
product: Windows
targetos: Windows
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_3D_0033
---

# D3D12DDI_COMMAND_LIST_FUNCS_3D_0033 structure


## -description


The command list functions for 3D.


## -syntax


````
typedef struct _D3D12DDI_COMMAND_LIST_FUNCS_3D_0033 {
  PFND3D12DDI_CLOSECOMMANDLIST                        pfnCloseCommandList;
  PFND3D12DDI_RESETCOMMANDLIST                        pfnResetCommandList;
  PFND3D12DDI_DRAWINSTANCED                           pfnDrawInstanced;
  PFND3D12DDI_DRAWINDEXEDINSTANCED                    pfnDrawIndexedInstanced;
  PFND3D12DDI_DISPATCH                                pfnDispatch;
  PFND3D12DDI_CLEAR_UNORDERED_ACCESS_VIEW_UINT_0003   pfnClearUnorderedAccessViewUint;
  PFND3D12DDI_CLEAR_UNORDERED_ACCESS_VIEW_FLOAT_0003  pfnClearUnorderedAccessViewFloat;
  PFND3D12DDI_CLEAR_RENDER_TARGET_VIEW_0003           pfnClearRenderTargetView;
  PFND3D12DDI_CLEAR_DEPTH_STENCIL_VIEW_0003           pfnClearDepthStencilView;
  PFND3D12DDI_DISCARD_RESOURCE_0003                   pfnDiscardResource;
  PFND3D12DDI_COPYTEXTUREREGION_0003                  pfnCopyTextureRegion;
  PFND3D12DDI_RESOURCECOPY                            pfnResourceCopy;
  PFND3D12DDI_COPYTILES                               pfnCopyTiles;
  PFND3D12DDI_COPYBUFFERREGION_0003                   pfnCopyBufferRegion;
  PFND3D12DDI_RESOURCERESOLVESUBRESOURCE              pfnResourceResolveSubresource;
  PFND3D12DDI_EXECUTE_BUNDLE                          pfnExecuteBundle;
  PFND3D12DDI_EXECUTE_INDIRECT                        pfnExecuteIndirect;
  PFND3D12DDI_RESOURCEBARRIER_0022                    pfnResourceBarrier;
  PFND3D12DDI_BLT                                     pfnBlt;
  PFND3D12DDI_PRESENT_0028                            pfnPresent;
  PFND3D12DDI_BEGIN_END_QUERY_0003                    pfnBeginQuery;
  PFND3D12DDI_BEGIN_END_QUERY_0003                    pfnEndQuery;
  PFND3D12DDI_RESOLVE_QUERY_DATA                      pfnResolveQueryData;
  PFND3D12DDI_SET_PREDICATION                         pfnSetPredication;
  PFND3D12DDI_IA_SETTOPOLOGY_0003                     pfnIaSetTopology;
  PFND3D12DDI_RS_SETVIEWPORTS_0003                    pfnRsSetViewports;
  PFND3D12DDI_RS_SETSCISSORRECTS_0003                 pfnRsSetScissorRects;
  PFND3D12DDI_OM_SETBLENDFACTOR                       pfnOmSetBlendFactor;
  PFND3D12DDI_OM_SETSTENCILREF                        pfnOmSetStencilRef;
  PFND3D12DDI_SET_PIPELINE_STATE                      pfnSetPipelineState;
  PFND3D12DDI_SET_DESCRIPTOR_HEAPS_0003               pfnSetDescriptorHeaps;
  PFND3D12DDI_SET_ROOT_SIGNATURE                      pfnSetComputeRootSignature;
  PFND3D12DDI_SET_ROOT_SIGNATURE                      pfnSetGraphicsRootSignature;
  PFND3D12DDI_SET_ROOT_DESCRIPTOR_TABLE               pfnSetComputeRootDescriptorTable;
  PFND3D12DDI_SET_ROOT_DESCRIPTOR_TABLE               pfnSetGraphicsRootDescriptorTable;
  PFND3D12DDI_SET_ROOT_32BIT_CONSTANT                 pfnSetComputeRoot32BitConstant;
  PFND3D12DDI_SET_ROOT_32BIT_CONSTANT                 pfnSetGraphicsRoot32BitConstant;
  PFND3D12DDI_SET_ROOT_32BIT_CONSTANTS_0003           pfnSetComputeRoot32BitConstants;
  PFND3D12DDI_SET_ROOT_32BIT_CONSTANTS_0003           pfnSetGraphicsRoot32BitConstants;
  PFND3D12DDI_SET_ROOT_BUFFER_VIEW                    pfnSetComputeRootConstantBufferView;
  PFND3D12DDI_SET_ROOT_BUFFER_VIEW                    pfnSetGraphicsRootConstantBufferView;
  PFND3D12DDI_SET_ROOT_BUFFER_VIEW                    pfnSetComputeRootShaderResourceView;
  PFND3D12DDI_SET_ROOT_BUFFER_VIEW                    pfnSetGraphicsRootShaderResourceView;
  PFND3D12DDI_SET_ROOT_BUFFER_VIEW                    pfnSetComputeRootUnorderedAccessView;
  PFND3D12DDI_SET_ROOT_BUFFER_VIEW                    pfnSetGraphicsRootUnorderedAccessView;
  PFND3D12DDI_IA_SET_INDEX_BUFFER                     pfnIASetIndexBuffer;
  PFND3D12DDI_IA_SET_VERTEX_BUFFERS_0003              pfnIASetVertexBuffers;
  PFND3D12DDI_SO_SET_TARGETS_0003                     pfnSOSetTargets;
  PFND3D12DDI_OM_SET_RENDER_TARGETS_0003              pfnOMSetRenderTargets;
  PFND3D12DDI_SET_MARKER                              pfnSetMarker;
  PFND3D12DDI_CLEAR_ROOT_ARGUMENTS                    pfnClearRootArguments;
  PFND3D12DDI_COPYBUFFERREGION_0003                   pfnAtomicCopyBufferRegion;
  PFND3D12DDI_OM_SETDEPTHBOUNDS_0025                  pfnOMSetDepthBounds;
  PFND3D12DDI_SETSAMPLEPOSITIONS_0027                 pfnSetSamplePositions;
  PFND3D12DDI_RESOURCERESOLVESUBRESOURCEREGION_0027   pfnResourceResolveSubresourceRegion;
  PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030        pfnSetProtectedResourceSession;
  PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032               pfnWriteBufferImmediate;
  PFND3D12DDI_SETVIEWINSTANCEMASK_0033                pfnSetViewInstanceMask;
} D3D12DDI_COMMAND_LIST_FUNCS_3D_0033, D3D12DDI_COMMAND_LIST_FUNCS_3D_0033;
````


## -struct-fields




### -field pfnCloseCommandList

Close the command list.


### -field pfnResetCommandList

Reset the command list.


### -field pfnDrawInstanced

Draw instanced.


### -field pfnDrawIndexedInstanced

Draw indexed instanced.


### -field pfnDispatch

Dispatch.


### -field pfnClearUnorderedAccessViewUint

Clear unordered access view unit.


### -field pfnClearUnorderedAccessViewFloat

Clear unordered access view float.


### -field pfnClearRenderTargetView

Clear render target view.


### -field pfnClearDepthStencilView

Clear depth stencil view.


### -field pfnDiscardResource

Discard resource.


### -field pfnCopyTextureRegion

Copy texture region.


### -field pfnResourceCopy

Resource copy.


### -field pfnCopyTiles

Copy tiles.


### -field pfnCopyBufferRegion

Copy buffer region.


### -field pfnResourceResolveSubresource

Resource resolve subresource.


### -field pfnExecuteBundle

Execute bundle.


### -field pfnExecuteIndirect

Execute indirect.


### -field pfnResourceBarrier

Resource barrier.


### -field pfnBlt

Blt.


### -field pfnPresent

Present.


### -field pfnBeginQuery

Begin query.


### -field pfnEndQuery

End query.


### -field pfnResolveQueryData

Resolve query data.


### -field pfnSetPredication

Set predication.


### -field pfnIaSetTopology

Set topology


### -field pfnRsSetViewports

Set view ports.


### -field pfnRsSetScissorRects

Set scissor rectangles.


### -field pfnOmSetBlendFactor

Set blend factor.


### -field pfnOmSetStencilRef

Set stencil reference.


### -field pfnSetPipelineState

Set pipeline state.


### -field pfnSetDescriptorHeaps

Set descriptor heaps.


### -field pfnSetComputeRootSignature

Set compute root signature.


### -field pfnSetGraphicsRootSignature

Set graphics root signature.


### -field pfnSetComputeRootDescriptorTable

Set compute root descriptor table.


### -field pfnSetGraphicsRootDescriptorTable

Set graphics root descriptor table.


### -field pfnSetComputeRoot32BitConstant

Set compute root 32-bit constant.


### -field pfnSetGraphicsRoot32BitConstant

Set graphics root 32-bit constant.


### -field pfnSetComputeRoot32BitConstants

Set compute root 32-bit constants.


### -field pfnSetGraphicsRoot32BitConstants

Set graphics root 32-bit constants.


### -field pfnSetComputeRootConstantBufferView

Set compute root constant buffer view.


### -field pfnSetGraphicsRootConstantBufferView

Set graphics root constant buffer view.


### -field pfnSetComputeRootShaderResourceView

Set compute root shader resource view.


### -field pfnSetGraphicsRootShaderResourceView

Set graphics root shader resource view.


### -field pfnSetComputeRootUnorderedAccessView

Set compute root unordered access view.


### -field pfnSetGraphicsRootUnorderedAccessView

Set graphics root unordered access view.


### -field pfnIASetIndexBuffer

Set index buffer.


### -field pfnIASetVertexBuffers

Set vertex buffers.


### -field pfnSOSetTargets

Set targets.


### -field pfnOMSetRenderTargets

Set render targets.


### -field pfnSetMarker

Set marker.


### -field pfnClearRootArguments

Clear root arguments.


### -field pfnAtomicCopyBufferRegion

Atomic copy buffer region.


### -field pfnOMSetDepthBounds

Set depth bounds.


### -field pfnSetSamplePositions

Set sample positions.


### -field pfnResourceResolveSubresourceRegion

Resource resolve subresource region.


### -field pfnSetProtectedResourceSession

Set protected resource session.


### -field pfnWriteBufferImmediate

Write buffer immediate.


### -field pfnSetViewInstanceMask

Set view instance mask.

