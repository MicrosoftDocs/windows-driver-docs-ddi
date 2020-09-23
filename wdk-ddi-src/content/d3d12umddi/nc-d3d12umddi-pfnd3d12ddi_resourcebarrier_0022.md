---
UID: NC:d3d12umddi.PFND3D12DDI_RESOURCEBARRIER_0022
title: PFND3D12DDI_RESOURCEBARRIER_0022 (d3d12umddi.h)
description: The pfnResourceBarrier callback function supports resource barriers.
old-location: display\pfnd3d12ddi_resourcebarrier_0022.htm
ms.assetid: AD42B7FC-9928-4386-B3EB-C9F0302415DA
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_RESOURCEBARRIER_0022 callback function"]
ms.keywords: PFND3D12DDI_RESOURCEBARRIER_0022, PFND3D12DDI_RESOURCEBARRIER_0022 callback, d3d12umddi/pfnResourceBarrier, display.pfnd3d12ddi_resourcebarrier_0022, pfnResourceBarrier, pfnResourceBarrier callback function [Display Devices]
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_RESOURCEBARRIER_0022
 - d3d12umddi/PFND3D12DDI_RESOURCEBARRIER_0022
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - pfnResourceBarrier
product:
 - Windows
---

# PFND3D12DDI_RESOURCEBARRIER_0022 callback function


## -description

The <i>pfnResourceBarrier</i> callback function supports resource barriers.

## -parameters

### -param Arg1

**hDrvCommandList**

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Count

Specifies a count.

### -param Arg3

**ResourceBarrier** [in]

A pointer to a resource barrier as a <a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddiarg_resource_barrier_0022">D3D12DDIARG_RESOURCE_BARRIER_0022</a> structure.

## -remarks

Access this callback function by using a command list functions structure, such as the <b>D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_0020</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddiarg_resource_barrier_0022">D3D12DDIARG_RESOURCE_BARRIER_0022</a>