---
UID: NC:d3dumddi.PFND3DDDI_QUERYRESOURCERESIDENCY
title: PFND3DDDI_QUERYRESOURCERESIDENCY (d3dumddi.h)
description: The QueryResourceResidency function determines the residency of the given list of resources.
old-location: display\queryresourceresidency.htm
tech.root: display
ms.assetid: 5b9a2a59-b2d1-468e-998b-902bc2a75cb3
ms.date: 05/10/2018
keywords: ["PFND3DDDI_QUERYRESOURCERESIDENCY callback function"]
ms.keywords: PFND3DDDI_QUERYRESOURCERESIDENCY, PFND3DDDI_QUERYRESOURCERESIDENCY callback, QueryResourceResidency, QueryResourceResidency callback function [Display Devices], UserModeDisplayDriver_Functions_2d646d44-dbbb-471d-9337-2cdf8c9a4245.xml, d3dumddi/QueryResourceResidency, display.queryresourceresidency
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: 
f1_keywords:
 - "d3dumddi/QueryResourceResidency"
 - "QueryResourceResidency"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - QueryResourceResidency
product:
 - Windows
---

# PFND3DDDI_QUERYRESOURCERESIDENCY callback function

## -description

The <i>QueryResourceResidency</i> function determines the residency of the given list of resources.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_queryresourceresidency">D3DDDIARG_QUERYRESOURCERESIDENCY</a> structure that describes a list of resources on which residency is verified.

## -returns

<i>QueryResourceResidency</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|All of the resources are in GPU-accessible memory.|
|S_RESIDENT_IN_SHARED_MEMORY|No allocations that comprise the resources are on disk. However, at least one allocation is not in GPU-accessible memory.|
|S_NOT_RESIDENT|At least one allocation that comprises the resources is on disk.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_OUTOFMEMORY|QueryResourceResidency could not allocate memory that is required for it to complete.|

## -remarks

The Microsoft Direct3D runtime calls the user-mode display driver's <i>QueryResourceResidency</i> function for applications to determine if the operating system will incur a significant stall at draw time if the system must make resources GPU-accessible. The information that is returned from <i>QueryResourceResidency</i> is an approximation of the residency of resources because the resources might become demoted before applications use the resources.

The user-mode display driver's <i>QueryResourceResidency</i> function must make calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresidencycb">pfnQueryResidencyCb</a> function. The <b>pfnQueryResidencyCb</b> function returns the residency status of a resource in the elements of the array that is specified by the <b>pResidencyStatus</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_queryresidency">D3DDDICB_QUERYRESIDENCY</a> structure. If <b>pfnQueryResidencyCb</b> returns D3DDDI_RESIDENCYSTATUS_NOTRESIDENT for any query, <i>QueryResourceResidency</i> must return S_NOT_RESIDENT. If <b>pfnQueryResidencyCb</b> returns D3DDDI_RESIDENCYSTATUS_RESIDENTINSHAREDMEMORY for any query and does not return D3DDDI_RESIDENCYSTATUS_NOTRESIDENT for any query, <i>QueryResourceResidency</i> must return S_RESIDENT_IN_SHARED_MEMORY. <i>QueryResourceResidency</i> must return S_OK only if all calls to <b>pfnQueryResidencyCb</b> for all queries return D3DDDI_RESIDENCYSTATUS_RESIDENTINGPUMEMORY.

For each resource that the runtime queries through a call to <i>QueryResourceResidency</i>, the user-mode display driver must determine which allocations that belong to the resource to query through a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresidencycb">pfnQueryResidencyCb</a>. For a resource that owns a single allocation, the determination is simple--the driver will query that allocation. However, if a resource owns multiple allocations, the determination is more difficult. The driver must determine which allocations that an application will likely use for rendering, and the driver must query only those allocations. For example, if a resource owns an allocation that is used for rendering and a scratch allocation that handles a lock operation, the driver should query only for the residency of the first allocation, because an application will most likely not use the second allocation for rendering.

<div class="alert"><b>Note</b>    Because the runtime does not support residency-querying of system memory resources, the runtime will always fail requests from applications for the residency status of system memory resources and will never call the user-mode display driver's <i>QueryResourceResidency</i> function for these system memory resources.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_queryresourceresidency">D3DDDIARG_QUERYRESOURCERESIDENCY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_queryresidency">D3DDDICB_QUERYRESIDENCY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresidencycb">pfnQueryResidencyCb</a>

