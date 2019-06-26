---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
title: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 (d3d12umddi.h)
description: The pfnCheckExistingResourceAllocationInfo callback function supports checking existing resource allocation information.
old-location: display\pfnd3d12ddi_checkexisitingresourceallocationinfo_0022.htm
ms.assetid: 428F23B4-3032-4BD9-A1C1-104BB2648F89
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022, PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback, d3d12umddi/pfnCheckExistingResourceAllocationInfo, display.pfnd3d12ddi_checkexisitingresourceallocationinfo_0022, pfnCheckExistingResourceAllocationInfo, pfnCheckExistingResourceAllocationInfo callback function [Display Devices]
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- pfnCheckExistingResourceAllocationInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback function


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_checkexisitingresourceallocationinfo_0022">pfnCheckExistingResourceAllocationInfo</a> callback function supports checking existing resource allocation information.


## -parameters




### -param Arg1

*hDevice*

A handle to the display device (graphics context).

### -param Arg2

hResource

A resource handle.

### -param *

pInfo [out]

Information for resource allocation.


## -returns



This callback function does not return a value.




## -remarks



This callback function is part of a two step process of resource creation. After the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0022">pfnCheckResourceAllocationInfo</a> callback function, the resource is created. During resource creation, the layout is never _UNDEFINED, since the driver will have returned a resolved texture layout. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0022">pfnCheckResourceAllocationInfo</a>
 

 

