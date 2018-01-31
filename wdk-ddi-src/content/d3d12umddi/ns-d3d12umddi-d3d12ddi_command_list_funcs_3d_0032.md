---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_3D_0032
title: D3D12DDI_COMMAND_LIST_FUNCS_3D_0032
author: windows-driver-content
description: The command list functions for 3D.
old-location: display\d3d12ddi-command-list-funcs-3d-0032.htm
old-project: display
ms.assetid: 9acd83c1-7e9e-4906-bb07-4f9699f76e96
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_3D_0032 structure [Display Devices], display.d3d12ddi-command-list-funcs-3d-0032, d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_3D_0032, D3D12DDI_COMMAND_LIST_FUNCS_3D_0032
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
-	D3D12DDI_COMMAND_LIST_FUNCS_3D_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_3D_0032
---

# D3D12DDI_COMMAND_LIST_FUNCS_3D_0032 structure


## -description


The command list functions for 3D.


## -syntax


````
typedef struct _D3D12DDI_COMMAND_LIST_FUNCS_3D_0032 {
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
} D3D12DDI_COMMAND_LIST_FUNCS_3D_0032, D3D12DDI_COMMAND_LIST_FUNCS_3D_0032;
````


## -struct-fields




#### - pfnCloseCommandList

Close the command list.


#### - pfnResetCommandList

Reset the command list.


#### - pfnDrawInstanced

Draw instanced.


#### - pfnDrawIndexedInstanced

Draw indexed instanced.


#### - pfnDispatch

Dispatch.


#### - pfnClearUnorderedAccessViewUint

Clear the unordered access view of UINT values.


#### - pfnClearUnorderedAccessViewFloat

Clear the unordered access view of FLOAT values.


#### - pfnClearRenderTargetView

Clear the render target view.


#### - pfnClearDepthStencilView

Clear the depth stencil view.


#### - pfnDiscardResource

Discard resource.


#### - pfnCopyTextureRegion

Copy texture region.


#### - pfnResourceCopy

Resource copy.


#### - pfnCopyTiles

Copy tiles.


#### - pfnCopyBufferRegion

Copy buffer region.


#### - pfnResourceResolveSubresource

Resource resolve subresource.


#### - pfnExecuteBundle

Execute bundle.


#### - pfnExecuteIndirect

Execute indirect.


#### - pfnResourceBarrier

Resource barrier.


#### - pfnBlt

Blt.


#### - pfnPresent

Present.


#### - pfnBeginQuery

Begin query.


#### - pfnEndQuery

End query.


#### - pfnResolveQueryData

Resolve query data.


#### - pfnSetPredication

Set predication.


#### - pfnIaSetTopology

Set topology.


#### - pfnRsSetViewports

Set view ports.


#### - pfnRsSetScissorRects

Set scissor rectangles.


#### - pfnOmSetBlendFactor

Set blend factor.


#### - pfnOmSetStencilRef

Set stencil reference.


#### - pfnSetPipelineState

Set pipeline state.


#### - pfnSetDescriptorHeaps

Set descriptor heaps.


#### - pfnSetComputeRootSignature

Set compute root signature.


#### - pfnSetGraphicsRootSignature

Set graphics root signature.


#### - pfnSetComputeRootDescriptorTable

Set compute root descriptor table.


#### - pfnSetGraphicsRootDescriptorTable

Set graphic root descriptor table.


#### - pfnSetComputeRoot32BitConstant

Set compute root 32-bit constant.


#### - pfnSetGraphicsRoot32BitConstant

Set graphics root 32-bit constant.


#### - pfnSetComputeRoot32BitConstants

Set compute root 32-bit constants.


#### - pfnSetGraphicsRoot32BitConstants

Set graphics root 32-bit constants.


#### - pfnSetComputeRootConstantBufferView

Set compute root constant buffer view.


#### - pfnSetGraphicsRootConstantBufferView

Set graphics root constant buffer view.


#### - pfnSetComputeRootShaderResourceView

Set compute root shader resource view.


#### - pfnSetGraphicsRootShaderResourceView

Set graphics root shader resource view.


#### - pfnSetComputeRootUnorderedAccessView

Set compute root unordered access view.


#### - pfnSetGraphicsRootUnorderedAccessView

Set graphics root unordered access view.


#### - pfnIASetIndexBuffer

Set index buffer.


#### - pfnIASetVertexBuffers

Set vertex buffers.


#### - pfnSOSetTargets

Set targets.


#### - pfnOMSetRenderTargets

Set render targets.


#### - pfnSetMarker

Set marker.


#### - pfnClearRootArguments

Clear root arguments.


#### - pfnAtomicCopyBufferRegion

Atomic copy the buffer region.


#### - pfnOMSetDepthBounds

Set depth bounds.


#### - pfnSetSamplePositions

Set sample positions.


#### - pfnResourceResolveSubresourceRegion

Resource resolve subresource region.


#### - pfnSetProtectedResourceSession

Set protected resource session.


#### - pfnWriteBufferImmediate

Write buffer immediate.

