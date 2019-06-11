---
UID: NC:d3dumddi.PFND3DDDI_SETPRIORITYCB
title: PFND3DDDI_SETPRIORITYCB (d3dumddi.h)
description: The pfnSetPriorityCb function sets the priority level of a resource or list of allocations.
old-location: display\pfnsetprioritycb.htm
tech.root: display
ms.assetid: 1812cb0f-9232-4813-9c7b-74c9fa4d03cf
ms.date: 05/10/2018
ms.keywords: D3Druntime_Functions_4bd6f90d-e958-43cc-8267-36d4d0448096.xml, PFND3DDDI_SETPRIORITYCB, PFND3DDDI_SETPRIORITYCB callback, d3dumddi/pfnSetPriorityCb, display.pfnsetprioritycb, pfnSetPriorityCb, pfnSetPriorityCb callback function [Display Devices]
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- pfnSetPriorityCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETPRIORITYCB callback function


## -description


The <i>pfnSetPriorityCb</i> function sets the priority level of a resource or list of allocations.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544265">D3DDDICB_SETPRIORITY</a> structure that describes the priority level to set a resource or list of allocations to.


## -returns



<i>pfnSetPriorityCb</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The priority level was successfully set.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.






## -remarks



The user-mode display driver can call the <i>pfnSetPriorityCb</i> function to set the priority of the underlying resource or list of allocations. If the priority level of a resource is set, all of the allocations that belong to the resource are set to the specified priority level. Typically, the user-mode display driver sets the priority of a resource or list of allocations after the Microsoft Direct3D runtime calls the user-mode display driver's <a href="https://msdn.microsoft.com/61ac2d28-7aed-4796-8d09-591db936013b">SetPriority</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a> function to set the eviction-from-memory priority for a resource. However, the user-mode display driver can set the priority of allocations at any time. 

After an application requests to set the priority level of a surface, the user-mode display driver should set the appropriate resource or list of allocations to the priority level that is specified by the application. 

<div class="alert"><b>Note</b>    Priority levels are only a hint to the video memory manager; they can be ignored by the memory manager under various conditions. </div>
<div> </div>
An allocation priority defines both the likelihood that the allocation remains resident and the likelihood of how hard the video memory manager will try to respect the driver's preference for the placement of the allocation. The following priority levels are defined in the D3dukmdt.h header file:



The driver can use priority levels other than the preceding defined values when appropriate. For example, marking an allocation with a priority level of 0x78000001 indicates that the allocation is slightly above normal. 


#### Examples

The following code example shows how to set priority level.

```cpp
HRESULT CD3DContext::SetPriority(CONST D3DDDIARG_SETPRIORITY* pSetPriority) {
    DWORD  dwSurfaceHandle = (DWORD)(DWORD_PTR)pSetPriority->hResource;
    CResource   &res = m_RTbl[dwSurfaceHandle];
    D3DDDICB_SETPRIORITY    setPri;
    UINT                    priority;

    priority = pSetPriority->Priority;

    memset(&setPri, 0, sizeof(setPri));

    setPri.hResource   = res.m_hResRuntime;
    setPri.pPriorities = &priority;

    return (m_d3dCallbacks.pfnSetPriorityCb(m_hD3D, &setPri));
}
```


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544265">D3DDDICB_SETPRIORITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/b6b142a4-20eb-4368-bd7f-8a25f4fe48ca">DxgkCbCreateContextAllocation</a>



<a href="https://msdn.microsoft.com/61ac2d28-7aed-4796-8d09-591db936013b">SetPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a>
 

 

