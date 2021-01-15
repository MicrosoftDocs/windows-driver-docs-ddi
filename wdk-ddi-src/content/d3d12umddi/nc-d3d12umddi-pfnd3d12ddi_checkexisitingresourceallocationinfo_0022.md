---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
title: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 (d3d12umddi.h)
description: The pfnCheckExistingResourceAllocationInfo callback function supports checking existing resource allocation information.
old-location: display\pfnd3d12ddi_checkexisitingresourceallocationinfo_0022.htm
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback function"]
ms.keywords: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022, PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback, d3d12umddi/pfnCheckExistingResourceAllocationInfo, display.pfnd3d12ddi_checkexisitingresourceallocationinfo_0022, pfnCheckExistingResourceAllocationInfo, pfnCheckExistingResourceAllocationInfo callback function [Display Devices]
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
 - PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
 - d3d12umddi/PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
product:
 - Windows
---

# PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback function


## -description

The <a href="/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_checkexisitingresourceallocationinfo_0022">pfnCheckExistingResourceAllocationInfo</a> callback function supports checking existing resource allocation information.

## -parameters

### -param Arg1

*hDevice*

A handle to the display device (graphics context).

### -param Arg2

hResource

A resource handle.

### -param Arg3

pInfo [out]

Information for resource allocation.

## -remarks

This callback function is part of a two step process of resource creation. After the <a href="/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0022">pfnCheckResourceAllocationInfo</a> callback function, the resource is created. During resource creation, the layout is never _UNDEFINED, since the driver will have returned a resolved texture layout.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0022">pfnCheckResourceAllocationInfo</a>

