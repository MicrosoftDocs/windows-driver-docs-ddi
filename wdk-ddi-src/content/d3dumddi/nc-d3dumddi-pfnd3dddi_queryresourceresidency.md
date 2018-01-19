---
UID: NC:d3dumddi.PFND3DDDI_QUERYRESOURCERESIDENCY
title: PFND3DDDI_QUERYRESOURCERESIDENCY
author: windows-driver-content
description: The QueryResourceResidency function determines the residency of the given list of resources.
old-location: display\queryresourceresidency.htm
old-project: display
ms.assetid: 5b9a2a59-b2d1-468e-998b-902bc2a75cb3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: QueryResourceResidency
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_QUERYRESOURCERESIDENCY callback



## -description
The <i>QueryResourceResidency</i> function determines the residency of the given list of resources.



## -prototype

````
PFND3DDDI_QUERYRESOURCERESIDENCY QueryResourceResidency;

__checkReturn HRESULT APIENTRY QueryResourceResidency(
  _In_       HANDLE                           hDevice,
  _In_ const D3DDDIARG_QUERYRESOURCERESIDENCY *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_queryresourceresidency.md">D3DDDIARG_QUERYRESOURCERESIDENCY</a> structure that describes a list of resources on which residency is verified.


## -returns
<i>QueryResourceResidency</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>All of the resources are in GPU-accessible memory.
<dl>
<dt><b>S_RESIDENT_IN_SHARED_MEMORY</b></dt>
</dl>No allocations that comprise the resources are on disk. However, at least one allocation is not in GPU-accessible memory.
<dl>
<dt><b>S_NOT_RESIDENT</b></dt>
</dl>At least one allocation that comprises the resources is on disk.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>QueryResourceResidency</i> could not allocate memory that is required for it to complete.

 


## -remarks
The Microsoft Direct3D runtime calls the user-mode display driver's <i>QueryResourceResidency</i> function for applications to determine if the operating system will incur a significant stall at draw time if the system must make resources GPU-accessible. The information that is returned from <i>QueryResourceResidency</i> is an approximation of the residency of resources because the resources might become demoted before applications use the resources.

The user-mode display driver's <i>QueryResourceResidency</i> function must make calls to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresidencycb.md">pfnQueryResidencyCb</a> function. The <b>pfnQueryResidencyCb</b> function returns the residency status of a resource in the elements of the array that is specified by the <b>pResidencyStatus</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_queryresidency.md">D3DDDICB_QUERYRESIDENCY</a> structure. If <b>pfnQueryResidencyCb</b> returns D3DDDI_RESIDENCYSTATUS_NOTRESIDENT for any query, <i>QueryResourceResidency</i> must return S_NOT_RESIDENT. If <b>pfnQueryResidencyCb</b> returns D3DDDI_RESIDENCYSTATUS_RESIDENTINSHAREDMEMORY for any query and does not return D3DDDI_RESIDENCYSTATUS_NOTRESIDENT for any query, <i>QueryResourceResidency</i> must return S_RESIDENT_IN_SHARED_MEMORY. <i>QueryResourceResidency</i> must return S_OK only if all calls to <b>pfnQueryResidencyCb</b> for all queries return D3DDDI_RESIDENCYSTATUS_RESIDENTINGPUMEMORY.

For each resource that the runtime queries through a call to <i>QueryResourceResidency</i>, the user-mode display driver must determine which allocations that belong to the resource to query through a call to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresidencycb.md">pfnQueryResidencyCb</a>. For a resource that owns a single allocation, the determination is simple--the driver will query that allocation. However, if a resource owns multiple allocations, the determination is more difficult. The driver must determine which allocations that an application will likely use for rendering, and the driver must query only those allocations. For example, if a resource owns an allocation that is used for rendering and a scratch allocation that handles a lock operation, the driver should query only for the residency of the first allocation, because an application will most likely not use the second allocation for rendering.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_queryresidency.md">D3DDDICB_QUERYRESIDENCY</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_queryresourceresidency.md">D3DDDIARG_QUERYRESOURCERESIDENCY</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresidencycb.md">pfnQueryResidencyCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_QUERYRESOURCERESIDENCY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

