---
UID: NC:d3d12umddi.PFND3D12DDI_BARRIER_0088
tech.root: display
title: PFND3D12DDI_BARRIER_0088
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_BARRIER_0088 callback function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_BARRIER_0088
f1_keywords:
 - PFND3D12DDI_BARRIER_0088
 - d3d12umddi/PFND3D12DDI_BARRIER_0088
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_BARRIER_0088
---

## -description

A driver's **PFND3D12DDI_BARRIER_0088** callback function synchronizes multiple accesses to resources. This callback supports enhanced barriers.

## -parameters

### -param hDrvCommandList

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param NumBarriers

The number of [**D3D12DDIARG_BARRIER_0088**](ns-d3d12umddi-d3d12ddiarg_barrier_0088.md) structures that **pBarriers** points to.

### -param pBarriers

Pointer to an array of [**D3D12DDIARG_BARRIER_0088**](ns-d3d12umddi-d3d12ddiarg_barrier_0088.md) structures that contain the enhanced barriers. The array size is specified by **NumBarriers**.

## -remarks

Drivers that report support for enhanced barriers must implement the **PFND3D12DDI_BARRIER** function. How drivers implement the **PFND3D12DDI_BARRIER** function is up to the hardware vendor, as long as they meet the design specifications and pass all related conformance tests.

Interestingly, a driver supporting enhanced barriers must expect even legacy ResourceBarrier API calls will also use the new PFND3D12DDI_BARRIER function. The legacy PFND3D12DDI_RESOURCEBARRIER_* table entry may be left as NULL. 


Access **PFND3D12DDI_BARRIER_0088** by using a command list functions structure such as the [**D3D12DDI_COMMAND_LIST_FUNCS_3D_0088**](ns-d3d12umddi-d3d12ddi_command_list_funcs_3d_0088.md) structure.

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDI_COMMAND_LIST_FUNCS_3D_0088**](ns-d3d12umddi-d3d12ddi_command_list_funcs_3d_0088.md)

[**D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0088**](ns-d3d12umddi-d3d12ddi_command_list_funcs_video_decode_0088.md)

[**D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0088**](ns-d3d12umddi-d3d12ddi_command_list_funcs_video_encode_0088.md)

[**D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0088**](ns-d3d12umddi-d3d12ddi_command_list_funcs_video_process_0088.md)

[**D3D12DDIARG_BARRIER_0088**](ns-d3d12umddi-d3d12ddiarg_barrier_0088.md)
