---
UID: NS:d3dumddi._D3DDDICB_SETDISPLAYMODE
title: _D3DDDICB_SETDISPLAYMODE (d3dumddi.h)
description: The D3DDDICB_SETDISPLAYMODE structure describes the primary allocation that is used to scan out to the display.
old-location: display\d3dddicb_setdisplaymode.htm
tech.root: display
ms.assetid: d2f6d53b-2dd7-46ed-8d1e-dea264da4046
ms.date: 05/10/2018
ms.keywords: D3DDDICB_SETDISPLAYMODE, D3DDDICB_SETDISPLAYMODE structure [Display Devices], D3D_param_Structs_4aeee940-b195-4020-ad42-b69a2f34f93e.xml, _D3DDDICB_SETDISPLAYMODE, d3dumddi/D3DDDICB_SETDISPLAYMODE, display.d3dddicb_setdisplaymode
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDICB_SETDISPLAYMODE
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_SETDISPLAYMODE
---

# _D3DDDICB_SETDISPLAYMODE structure


## -description


The D3DDDICB_SETDISPLAYMODE structure describes the primary allocation that is used to scan out to the display. 


## -struct-fields




### -field hPrimaryAllocation

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the primary allocation for scanning out. The Microsoft Direct3D runtime's <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function returns this handle. 


### -field PrivateDriverFormatAttribute

[out] A private format attribute that the user-mode display driver should use to convert the current primary surface if the <a href="https://msdn.microsoft.com/a1f58757-809d-4351-8b1a-fd4420981c24">pfnSetDisplayModeCb</a> callback function returned D3DDDIERR_INCOMPATIBLEPRIVATEFORMAT. 


## -remarks



The user-mode display driver can set the <b>hPrimaryAllocation</b> member in the call to <a href="https://msdn.microsoft.com/a1f58757-809d-4351-8b1a-fd4420981c24">pfnSetDisplayModeCb</a> to scan out any allocation. However, the allocation must be marked as a primary (that is, the user-mode display driver must have set the <b>Primary</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a> structure in a call to the <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function to create the allocation).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a>



<a href="https://msdn.microsoft.com/a1f58757-809d-4351-8b1a-fd4420981c24">pfnSetDisplayModeCb</a>
 

 

